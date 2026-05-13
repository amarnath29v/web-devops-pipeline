pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/amarnath29v/web-devops-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t web-devops-app .'
            }
        }

        stage('Remove Old Container') {
            steps {
                bat 'docker rm -f web-container || exit 0'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 8081:80 --name web-container web-devops-app'
            }
        }
    }
}