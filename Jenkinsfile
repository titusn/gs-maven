pipeline {
    agent { docker 'maven:3.3.9' }
    stages {
        stage ('Clone sources') {
            steps {
                git url: 'https://github.com/titusn/gs-maven.git'
            }
        }

        stage ('Artifactory configuration') {
            steps {
                // Tool name from Jenkins configuration
                rtMaven.tool = "Maven-3.3.9"
                // Set Artifactory repositories for dependencies resolution and artifacts deployment.
                //rtMaven.deployer releaseRepo:'libs-release-local', snapshotRepo:'libs-snapshot-local', server: server
                //rtMaven.resolver releaseRepo:'libs-release', snapshotRepo:'libs-snapshot', server: server
            }
        }

        stage ('Maven build') {
            steps {
                def buildInfo = rtMaven.run pom: 'gs-maven/pom.xml', goals: 'clean install'
            }
        }
    }
}