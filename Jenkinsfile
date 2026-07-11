pipeline {
    agent any

    environment {
        COMPOSE_PROJECT_NAME = 'wordpress-docker'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/JosephOrtiz/wordpress-docker-jenkins.git'
            }
        }

        stage('Down') {
            steps {
                sh 'docker compose down'
            }
        }

        stage('Up') {
            steps {
                sh 'docker compose up -d'
            }
        }

        stage('Verify') {
            steps {
                sh 'docker ps'
            }
        }
    }
}