pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Crear archivo de entorno') {
            steps {
                bat 'copy /Y .env.example .env'
            }
        }

        stage('Detener contenedores') {
            steps {
                bat 'docker compose -p wordpress-jenkins down'
            }
        }

        stage('Levantar contenedores') {
            steps {
                bat 'docker compose -p wordpress-jenkins up -d'
            }
        }

        stage('Verificar despliegue') {
            steps {
                bat 'docker ps'
            }
        }
    }
}