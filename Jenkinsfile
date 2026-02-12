pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Sobika-E/eg.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t eg-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop eg-container || true'
                sh 'docker rm eg-container || true'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8091:80 --name eg-container eg-app'
            }
        }
    }
}

