pipeline {
    agent any
    tools {
        jdk 'jdk17'
        maven 'Maven3'
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/hakshianu-dotcom/11.git'
            }
        }
        stage('Build & Test') {
            steps {
                echo "Building and running tests..."
                bat 'mvn clean test'
            }
        }
    }
    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
    }
}