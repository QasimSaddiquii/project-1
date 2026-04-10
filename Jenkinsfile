pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/QasimSaddiquii/project-1.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker stop myapp || true'
                sh 'docker rm myapp || true'
                sh 'docker run -d --name myapp -p 8081:80 app'
            }
        }
    }
}
