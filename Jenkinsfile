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
                bat 'npm install'
            }
        }

        stage('Run tests') {
            steps {
                echo " Exécution des tests..."
               
                bat 'npm test -- --runInBand'
            }
        }

        stage('Build Docker image') {
            steps {
                echo "Build de l\'image Docker..." 
                bat 'docker build -t todo-app .'
            }
        }
    }
}
