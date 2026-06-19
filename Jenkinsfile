pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                git 'https://github.com/ganeshgunasekaran0107-devops/Jenkins-Declarative-pipeline-script.git'
            }
        }

        stage('Build Backend JAR') {
            steps {
                dir('backend') {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Build Frontend WAR') {
            steps {
                dir('frontend') {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Deploy Backend') {
            steps {
                sh 'mkdir -p /opt/backend'
                sh 'cp backend/target/*.jar /opt/backend/'
            }
        }

        stage('Deploy Frontend') {
            steps {
                sh 'cp frontend/target/*.war /opt/apache-tomcat-7.0.109/webapps/'
            }
        }

    }
}