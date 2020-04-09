pipeline {
    agent any

    stages {
        stage ('Clone') {
            steps {
                git branch: 'master', url: "https://github.com/sputturu/cphtest.git"
            }
        }

        stage ('Artifactory configuration') {
            steps {
                rtServer (
                    id: "jenkins-artifactory-server",
                    url: "http://3.135.19.191/artifactory",
                    credentialsId: "articred"
                )

                rtGradleDeployer (
                    id: "GRADLE_DEPLOYER",
                    serverId: "jenkins-artifactory-server",
                    repo: "libs-release-local",
                )

                rtGradleResolver (
                    id: "GRADLE_RESOLVER",
                    serverId: "jenkins-artifactory-server",
                    repo: "jcenter"
                )
            }
        }

        stage ('Exec Gradle') {
            steps {
                rtGradleRun (
                    tool: "Gradle", // Tool name from Jenkins configuration
                    rootDir: 'src/main/java/',
                    buildFile: 'build.gradle',
                    tasks: 'clean artifactoryPublish',
                    deployerId: "GRADLE_DEPLOYER",
                    resolverId: "GRADLE_RESOLVER"
                )
            }
        }

        stage ('Publish build info') {
            steps {
                rtPublishBuildInfo (
                    serverId: "jenkins-artifactory-server"
                )
            }
        }
    }
}
