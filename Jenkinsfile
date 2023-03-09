pipeline {
    agent any
    
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    def image = "flask-app"
                    sh "docker build -t '${image}' ."
              }
            }
        }
        stage('Push docker image to dockerhub') {
            steps {
                script {
                    def registry = "noabenhamo/flask-app-jenkins-pipeline-project"
                    
                    // login to dockerhub
                    sh "docker login -u noabenhamo -p ${{ secrets.DOCKERHUB_PASS }}"
                    
                    // push the docker image to dockerhub
                    sh "docker push '${registry}:latest'"
              }
            }
        
        }
    }
 }
