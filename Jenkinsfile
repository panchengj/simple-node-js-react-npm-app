pipeline {
    agent {
        docker {
            image 'node:7-alpine' 
            args '-p 3006:3000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}
