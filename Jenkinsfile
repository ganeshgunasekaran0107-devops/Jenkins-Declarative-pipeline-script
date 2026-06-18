pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                git 'https://github.com/ganeshgunasekaran0107-devops/Jenkins-Declarative-pipeline-script.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'cp target/*.jar /opt/tomcat/webapps/'
            }
        }
    }
}