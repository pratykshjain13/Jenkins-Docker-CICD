
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking source code'
                sh 'ls -l'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Docker Image using Compose'
                sh 'docker compose build'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing application using Docker Compose'

                sh '''
                    docker compose up -d

                    sleep 3

                    curl -fsS http://127.0.0.1:8083/ | grep -q "Your Project is Completed"
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application using Docker Compose'

                sh '''
                    docker compose up -d
                    docker compose ps
                '''
            }
        }
    }

    post {
        success {
            echo 'Docker Compose CI/CD Pipeline Completed Successfully!'
        }

        failure {
            echo 'Docker Compose CI/CD Pipeline Failed!'
        }
    }
}

