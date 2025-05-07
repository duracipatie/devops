pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker build -t java-maven-app .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker run --rm java-maven-app'
            }
        }
    }
}
