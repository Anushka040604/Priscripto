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
                    sh 'npm install'
                }
            }
        }

        stage('Install Frontend Dependencies') {
            steps {
                dir('frontend') {
                    sh 'npm install'
                }
            }
        }

        stage('Install Backend Dependencies') {
            steps {
                dir('backend') {
                    sh 'npm install'
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
