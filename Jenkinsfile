pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t apoorvaantappa/devops-app:latest ./docker-app'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop myapp || true
                docker rm myapp || true
                docker run -d -p 5000:5000 --name myapp apoorvaantappa/devops-app:latest
                '''
            }
        }

    }
}
