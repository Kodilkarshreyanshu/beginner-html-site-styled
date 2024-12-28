pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t shreyanshuk/website:latest .'
                sh 'docker push shreyanshuk/website:latest'
            }
        }
        stage('Deploy') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
