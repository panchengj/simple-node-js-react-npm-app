pipeline {
    agent {
        docker {
            image 'node:14-alpine' 
            args '-p 3006:3000' 
        }
    }

    enviroment{ 
                 CI = 'true'
             }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Test'){
            steps {  
              sh './jenkins/scripts/test.sh'
         }
       }
    }
}
