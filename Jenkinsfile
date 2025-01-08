pipeline {
    agent any
    stages {
        stage('Clonare') {
            steps {
                git 'https://github.com/valy31/hello-world-pipeline.git'
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Building Hello World App"'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running Tests"'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying Application"'
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker build -t hello-world-app .'
            }
        }
    }
}
