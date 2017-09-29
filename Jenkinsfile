#!groovy

pipeline {
    agent any
    tools {
        maven 'mvn-3'
    }
    stages {
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
