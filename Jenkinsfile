#!groovy

pipeline {
    agent { docker 'maven:3.3.9' }
    tools {
        maven 'maven_latest'
        jdk 'jdk_latest'
    }
    environment {
        JAVA_HOME = tool 'jdk_latest'
    }
    stages {
        stage ('Clone sources') {
            steps {
                git url: 'https://github.com/titusn/gs-maven.git'
            }
        }

        stage ('Maven clean') {
            steps {
                sh "echo $JAVA_HOME"
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