#!groovy​
pipeline {
    agent { docker 'maven:3.3.9' }
    stages {
        String m2Tool = tool 'mvn-3'
        stage ('Clone sources') {
            steps {
                git url: 'https://github.com/titusn/gs-maven.git'
            }
        }

        stage ('Artifactory configuration') {
            steps {
                // Set Artifactory repositories for dependencies resolution and artifacts deployment.
                //rtMaven.deployer releaseRepo:'libs-release-local', snapshotRepo:'libs-snapshot-local', server: server
                //rtMaven.resolver releaseRepo:'libs-release', snapshotRepo:'libs-snapshot', server: server
            }
        }

        stage ('Maven build') {
            steps {
                withEnv(["M2_HOME=$m2Tool"]) {
                    String mvn = "\"$m2Tool/bin/mvn\" ${mvnOptions.join(' ')} $mavenArgs"
                    cli "$mvn clean install"
                }
            }
        }
    }
}