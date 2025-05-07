pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/duracipatie/devops.git'
            }
        }
        
        stage('Compile') {
            steps {
                echo 'Compiler'
                bat 'mvn clean install'
            }
        }
        
         stage('Sonar Analysis') {
            steps {
                echo 'Analyse Sonar'
                 
            }
        }
        
        stage('Build image Docker') {
            steps {
                echo 'Build image Docker'
                bat "docker build -t dxc/devops:latest ."
            }
        }
        
        stage('Publie l\'image') {
            steps {
                echo 'Publie l\'image dans le registry'
            }
        }
        
        stage('Exécuter l\'image - Conteneur') {
            steps {
                echo 'Publie l\'image dans le registry'
                bat "docker run --rm dxc/devops:latest"
            }
        }
    }
}
