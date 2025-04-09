pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Admin Dependencies') {
            steps {
                dir('admin') {
                    bat 'npm install'
                }
            }
        }

        stage('Install Frontend Dependencies') {
            steps {
                dir('frontend') {
                    bat 'npm install'
                }
            }
        }

        stage('Install Backend Dependencies') {
            steps {
                dir('backend') {
                    bat 'npm install'
                }
            }
        }
    }

    post {
        success {
            echo '✅ All dependencies installed successfully!'
        }
        failure {
            echo '❌ Something went wrong!'
        }
    }
}
