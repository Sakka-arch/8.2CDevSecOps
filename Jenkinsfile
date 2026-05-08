pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Sakka-arch/8.2CDevSecOps.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test || true'
            }
        }

        stage('Security Scan') {
            steps {
                sh 'npm audit || true'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage complete (no build step required for this app)'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'SUCCESS: Pipeline completed successfully.'
        }
        failure {
            echo 'FAILED: Check logs.'
        }
    }
}