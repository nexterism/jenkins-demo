pipeline {
    agent any
    options {
        // Stops Jenkins from trying to peek at a "dirty" folder
        skipDefaultCheckout(true) 
    }
    stages {
        stage('Clean and Clone') {
            steps {
                // Deletes everything in the current workspace folder
                cleanWs() 
                // Now pulls a fresh, clean copy from your GitHub
                checkout scm 
            }
        }
        // Your existing Build and Run stages follow...
    }
}
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
