#!groovy

pipeline {
    agent {
        dockerfile {
            filename 'Dockerfile'
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
