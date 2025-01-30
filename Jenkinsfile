pipeline {
    agent any

    stages {

        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }

        stage('Test') {
            steps {

                sh 'chmod +x jenkins/scripts/test.sh'
                sh 'ls -l jenkins/scripts/test.sh' // Debugging step

                sh './jenkins/scripts/test.sh'
            }
        }

stage('Deliver') {
            steps {
                
                sh 'chmod +x jenkins/scripts/deliver.sh'
                sh 'ls -l jenkins/scripts/deliver.sh' // Debugging step

                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
 
   }

}
