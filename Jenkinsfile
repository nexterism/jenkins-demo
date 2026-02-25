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
