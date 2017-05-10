#!groovy
pipeline {
    agent { docker 'maven:3.3.9' }
    environment {
        def maven = tool name: 'maven_latest', type: 'maven'
    }
    stages {
        stage ('Clone sources') {
            steps {
                git url: 'https://github.com/titusn/gs-maven.git'
            }
        }

        stage ('Maven clean') {
            steps {
                sh '$maven clean'
            }
        }

        stage ('Maven compile') {
            steps {
                sh '$maven compile'
            }
        }

        stage ('Maven test') {
            steps {
                sh '$maven test'
            }
        }

        stage ('Maven install') {
            steps {
                sh '$maven install'
            }
        }
    }
}