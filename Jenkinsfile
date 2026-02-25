pipeline {
    agent any 
    
    options {
        // Keeps the environment stable by not double-checking out code
        skipDefaultCheckout(true)
    }

    stages {
        stage('Clean and Clone') {
            steps {
                cleanWs()
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                // This builds the actual game component
                sh 'docker build -t my-game-app:${BUILD_NUMBER} .'
            }
        }

        stage('Run in Container') {
            steps {
                // This ensures the game runs in an isolated, high-performing environment
                sh 'docker run --rm my-game-app:${BUILD_NUMBER}'
            }
        }
    }
}
