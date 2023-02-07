pipeline {
    agent any
    
    stages {
        stage('Build Docker Image') {
            steps {
                def image = "flask-app"
                sh "docker build -t '${image}' ."
            }
        stage('Push docker image to dockerhub') {
            steps {
                def registry = "noabenhamo/flask-app-jenkins-pipeline-project"
                
                // login to dockerhub
                sh "docker login -u noabenhamo -p Aa123456123456"

                // push the docker image to dockerhub
                sh "docker push '${registry}:latest'"
            }
        
        }
    }
}
