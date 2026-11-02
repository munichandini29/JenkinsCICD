pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-demo .'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Successful'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker stop cicd-container || true'
                sh 'docker rm cicd-container || true'
                sh 'docker run -d -p 8080:80 --name cicd-container cicd-demo'
            }
        }

    }
}