pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "kavya107/finance-manager:1.0"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Kavya-107/finance-tracker-devops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push $DOCKER_IMAGE'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/deployment.yaml'
                sh 'kubectl apply -f k8s/service.yaml'
            }
        }
    }
}