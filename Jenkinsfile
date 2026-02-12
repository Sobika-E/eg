pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Sobika-E/eg.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-nginx-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop my-container || true'
                sh 'docker rm my-container || true'
                sh 'docker run -d -p 8081:80 --name my-container my-nginx-app'
            }
        }
    }
}
