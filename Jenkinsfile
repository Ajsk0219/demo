pipeline {
    agent any
    tools {
        maven 'Maven3'
        jdk 'JDK8'
    }
    stages {
        stage('Code Validate') {
            steps {
                sh 'mvn validate'
            }
        }
        stage('Code Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Code test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Packaging') {
            steps {
                sh 'mvn packaging'
            }
        }
    }
    post{
        success{
            junit 'target/surefire-reports/*.xml'
        }
    }
}
