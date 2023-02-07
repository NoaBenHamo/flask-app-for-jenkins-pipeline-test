pipeline {
    agent {
        docker {
            image 'python:3.11.1-alpine3.16'
        }
    }
    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app:latest .'
            }
        }
    }
}
