pipeline {
    agent any

    environment {
        COMPOSE_PROJECT_NAME = "Prescripto"
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo "Cloning project repo..."
                git 'https://github.com/ayushmahandule1208/Priscripto.git'
            }
        }

        stage('Build Images') {
            steps {
                echo "Building Docker images..."
                sh 'docker-compose build'
            }
        }

        stage('Start Containers') {
            steps {
                echo "Starting services with Docker Compose..."
                sh 'docker-compose up -d'
            }
        }
    }

    post {
        always {
            echo "Cleaning up containers after pipeline run..."
            sh 'docker-compose down'
        }
    }
}
