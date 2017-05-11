#!groovy

pipeline {
    agent {
        dockerfile {
            filename 'Dockerfile'
            args '-H 10.1.10:150:2375'
        }
    }
    stages {
        stage ('Clone sources') {
            steps {
                checkout scm
            }
        }

        stage ('Maven clean') {
            steps {
                sh "mvn clean"
            }
        }

        stage ('Maven install') {
            steps {
                sh "mvn install"
            }
        }
    }
    post {
        success {
            echo "Successfully built."
        }
    }
}