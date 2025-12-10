pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo " Récupération du code depuis Git..."
                checkout scm
            }
        }

        stage('Install dependencies') {
            steps {
                echo " Installation des dépendances Node..."
                sh 'npm install'
            }
        }

        stage('Run tests') {
            steps {
                echo " Exécution des tests..."
                sh 'npm test'
            }
        }

        stage('Build Docker image') {
            steps {
                echo "Build de l\'image Docker..."
                sh 'docker build -t todo-app .'
            }
        }
    }
}
