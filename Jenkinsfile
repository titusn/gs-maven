#!groovy

pipeline {
    agent { docker 'maven:3.3.9-jdk-8' }
    stages {
        stage ('Clone sources') {
            steps {
                git url: 'https://github.com/titusn/gs-maven.git'
            }
        }

        stage ('Maven clean') {
            steps {
                sh "mvn clean"
            }
        }

        stage ('Maven compile') {
            steps {
                sh "mvn compile"
            }
        }

        stage ('Maven test') {
            steps {
                sh "mvn test"
            }
        }

        stage ('Maven install') {
            steps {
                sh "mvn install"
            }
        }
    }
}