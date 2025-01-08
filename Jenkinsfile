pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/username/hello-world-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Building the application'
                }
            }
        }

        stage('Docker Build') {
            steps {
                script {
                    echo 'Building Docker image'
                    sh 'docker build -t hello-world-app .'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Running Docker container'
                    sh 'docker run -d -p 8080:8080 hello-world-app'
                }
            }
        }
    }
}
