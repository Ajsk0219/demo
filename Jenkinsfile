pipeline {
    agent { node { label 'Lab-Agent' } }
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
        stage('Packing') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post{
        success{
            junit 'target/surefire-reports/*.xml'
        }
    }
}
