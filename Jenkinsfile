pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/ganeshgunasekaran0107-devops/Jenkins-Declarative-pipeline-script.git'
            }
        }

        stage('Dependencies') {
            steps {
                sh 'flutter pub get'
            }
        }

        stage('Analyze') {
            steps {
                sh 'flutter analyze'
            }
        }

        stage('Test') {
            steps {
                sh 'flutter test'
            }
        }

        stage('Build APK') {
            steps {
                sh 'flutter build apk'
            }
        }
    }

    post {

        success {
            echo 'APK Build Successful'
        }

        failure {
            echo 'APK Build Failed'
        }
    }
}