#!groovy

def mavendir = tool 'maven_latest'
def maven = "$mavendir/bin/mvn"
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
                sh "$maven clean"
            }
        }

        stage ('Maven compile') {
            steps {
                sh "$maven compile"
            }
        }

        stage ('Maven test') {
            steps {
                sh "$maven test"
            }
        }

        stage ('Maven install') {
            steps {
                sh "$maven install"
            }
        }
    }
}