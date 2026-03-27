pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Kavya-107/Finance-Tracker-devops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t finance-tracker .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 3000:3000 finance-tracker'
            }
        }

    }
}
