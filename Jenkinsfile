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
            String m2Tool = tool 'mvn-3'
            steps {
                withEnv(["M2_HOME=$m2Tool"]) {
                    String mvn = "\"$m2Tool/bin/mvn\" ${mvnOptions.join(' ')} $mavenArgs"
                    cli "$mvn clean install"
                }
            }
        }
    }
}