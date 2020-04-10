node {
    def server
    def buildInfo
    def rtGradle
    
    stage ('Clone') {
        git url: 'https://github.com/sputturu/cphtest.git'
    }
 
    stage ('Artifactory configuration') {
        // Obtain an Artifactory server instance, defined in Jenkins --> Manage:
        server = Artifactory.server 'jenkins-artifactory-server'

        rtGradle = Artifactory.newGradleBuild()
        rtGradle.tool = Gradle // Tool name from Jenkins configuration
        rtGradle.deployer repo: 'libs-release-local', server: server
        rtGradle.resolver repo: 'libs-release', server: server
        rtGradle.deployer.deployArtifacts = false // Disable artifacts deployment during Gradle run
        
        buildInfo = Artifactory.newBuildInfo()
    }
 
    stage ('Test') {
        rtGradle.run buildFile: 'build.gradle', tasks: 'clean test'
    }
 
    stage ('Deploy') {
        rtGradle.run buildFile: 'build.gradle', tasks: 'artifactoryPublish', buildInfo: buildInfo
        rtGradle.deployer.deployArtifacts buildInfo
    }
    
    stage ('Publish build info') {
        server.publishBuildInfo buildInfo
    }
}

