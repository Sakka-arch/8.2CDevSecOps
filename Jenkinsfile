pipeline {
    agent any

    stages {

        stage('Checkout') {
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
    }
}