pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                git 'https://github.com/ganeshgunasekaran0107-devops/Jenkins-Declarative-pipeline-script.git'
            }
        }

               stage('Java Check') {
               steps {
                    sh 'echo $JAVA_HOME'
                    sh 'java -version'
                    sh 'javac -version'
                    sh 'mvn -version'
                }
        }

        
        

        stage('Build Backend JAR') {
                environment {
                    JAVA_HOME = '/usr/lib/jvm/java-21-openjdk-amd64'
                    PATH = "${JAVA_HOME}/bin:${PATH}"
                }
            steps {
                dir('backend') {
                    sh 'java -version'
                    sh 'javac -version'
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