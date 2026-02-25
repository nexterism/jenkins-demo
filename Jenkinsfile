pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                // We don't need the URL here anymore because Jenkins 
                // will already be inside the repo!
                checkout scm
            }
        }
        stage('Run Python') {
            steps {
                sh 'python3 app.py'
            }
        }
    }
}
