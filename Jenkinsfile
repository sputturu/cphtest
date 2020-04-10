node {
    // Get Artifactory server instance, defined in the Artifactory Plugin administration page.
    def server = Artifactory.server "jenkins-artifactory-server"
    // Create an Artifactory Gradle instance.
    def rtGradle = Artifactory.newGradleBuild()
    def buildInfo

    stage('Clone sources') {
        git url: 'https://github.com/sputturu/cphtest.git'
    }

    stage('Artifactory configuration') {
        // Tool name from Jenkins configuration
        rtGradle.tool = "Gradle"
        // Set Artifactory repositories for dependencies resolution and artifacts deployment.
        rtGradle.deployer repo:'libs-release-local', server: server
        rtGradle.resolver repo:'libs-release', server: server
    }

    stage('Gradle build') {
        buildInfo = rtGradle.run rootDir: "/tree/master/gradle", buildFile: 'build.gradle', tasks: 'clean artifactoryPublish'
    }

    stage('Publish build info') {
        server.publishBuildInfo buildInfo
    }
}
