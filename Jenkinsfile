#!groovy

pipeline {
    agent { docker 'maven:3.3.9' }
    stages {
        stage ('Clone sources') {
            steps {
                git url: 'https://github.com/titusn/gs-maven.git'
            }
        }

        stage ('Maven clean') {
            steps {
                sh "${tool 'maven_latest'}/bin/mvn clean"
            }
        }

        stage ('Maven compile') {
            steps {
                sh "${tool 'maven_latest'}/bin/mvn compile"
            }
        }

        stage ('Maven test') {
            steps {
                sh "${tool 'maven_latest'}/bin/mvn test"
            }
        }

        stage ('Maven install') {
            steps {
                sh "${tool 'maven_latest'}/bin/mvn install"
            }
        }
    }
}