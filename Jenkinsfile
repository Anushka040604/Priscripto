pipeline {
    agent any

    environment {
        COMPOSE_PROJECT_NAME = "Prescripto"
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo "Cloning project repo..."
                git url: 'https://github.com/Anushka040604/Priscripto.git', branch: 'main'
            }
        }

        stage('Build Images') {
            steps {
                echo "Building Docker images..."
                sh 'docker-compose -f docker-compose.yml build'
            }
        }

        stage('Start Containers') {
            steps {
                echo "Starting services with Docker Compose..."
                sh 'docker-compose -f docker-compose.yml up -d'
            }
        }
    }

    post {
        always {
            echo "Cleaning up containers after pipeline run..."
            sh 'docker-compose -f docker-compose.yml down'
        }
    }
}
