pipeline {
    agent {
        docker {
            image 'node:14-alpine' 
            args '-p 3006:3000' 
        }
    }

    environment{ 
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
              sh 'printenv'
            }
         }
       stage(Deliver) {
           steps{
              sh './jenkins/scripts/deliver.sh'
              input message: 'Finished using the web site? (Click "Proceed" to continue)'
              sh './jenkins/scripts/kill.sh'
         }      
     }
}
}
