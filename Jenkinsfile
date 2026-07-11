pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Detener contenedores') {
            steps {
                bat 'docker compose down'
            }
        }

        stage('Levantar contenedores') {
            steps {
                bat 'docker compose up -d'
            }
        }

        stage('Verificar despliegue') {
            steps {
                bat 'docker ps'
            }
        }
    }
}