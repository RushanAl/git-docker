pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Specify the branch 'main' explicitly
                git branch: 'main', url: 'https://github.com/RushanAl/git-docker.git'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy the application using Docker Compose
                    sh 'docker-compose down' 
                    sh 'docker-compose build' // Stop any running containers
                    sh 'docker-compose up -d' // Start the application in detached mode
                }
            }
        }
    }

}