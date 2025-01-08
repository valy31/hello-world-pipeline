pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/valy31/hello-world-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t hello-world-app .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 5000:5000 hello-world-app'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh 'curl http://localhost:5000'
                }
            }
        }

        stage('Cleanup') {
            steps {
                script {
                    sh 'docker stop $(docker ps -q --filter "ancestor=hello-world-app")'
                    sh 'docker rm $(docker ps -a -q --filter "ancestor=hello-world-app")'
                }
            }
        }
    }
}
