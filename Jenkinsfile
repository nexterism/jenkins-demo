pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                // This creates a 'package' of your app
                sh 'docker build -t my-game-app:${BUILD_NUMBER} .'
            }
        }
        stage('Run in Container') {
            steps {
                // This runs your app inside its own isolated world
                sh 'docker run --rm my-game-app:${BUILD_NUMBER}'
            }
        }
    }
}
