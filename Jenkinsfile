pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub'
                sh 'ls -l'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Docker Image'
                sh 'docker build -t webapp:v1 .'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Docker Container'

                sh '''
                    docker rm -f webapp-test || true

                    docker run -d \
                    --name webapp-test \
                    -p 18081:80 \
                    webapp:v1

                    sleep 3

                    curl -fsS http://127.0.0.1:18081/ | grep -q "Welcome to My Docker CI/CD Project!"
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application'

                sh '''
                    docker rm -f webapp || true

                    docker run -d \
                    --name webapp \
                    -p 8082:80 \
                    webapp:v1
                '''
            }
        }
    }

    post {
        always {
            sh 'docker rm -f webapp-test || true'
        }

        success {
            echo 'CI/CD Pipeline Completed Successfully!'
        }

        failure {
            echo 'CI/CD Pipeline Failed!'
        }
    }
}
