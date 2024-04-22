pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the repository
                git branch: 'main', url: 'https://github.com/NuranR/EE6262.git'
            }
        }
        stage('Dockerize the Application') {
            steps {
                // Build Docker image
                script {
                    docker.build('ode-app')
                }
            }
        }
        stage('Run Container') {
            steps {
                // Run Docker container
                script {
                    docker.image('node-app').run('-p 5000:5000')
                }
            }
        }
    }
}