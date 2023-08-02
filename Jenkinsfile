pipeline {
    agent any
    tools {
        maven "maven-3.9.3"
        jdk "jdk-17"
    }

    stages {
        stage("init"){
            steps{
                script {
                    git branch: 'main', url: 'https://github.com/kellychoko/wordsmith-api.git'
                }
            }
        }

        stage("Build Artifact") {
            steps {
                script {
                    sh "java --version"
                    sh "mvn clean install"
                }
            }
        }

        stage("Unit Test") {
            steps {
                script {
                    sh "mvn test"
                }
            }
        }
    }
}