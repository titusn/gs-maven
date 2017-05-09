#!groovy​
pipeline {
    agent { docker 'maven:3.3.9' }
    stages {
        stage ('Clone sources') {
            steps {
                git url: 'https://github.com/titusn/gs-maven.git'
            }
        }

        stage ('Maven build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}