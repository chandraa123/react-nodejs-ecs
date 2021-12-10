pipeline {
    agent any
      
      tools {
          nodejs "default"
      }
    environment { 
        CI = 'true'
    }
      stages {
        stage('init') {
            steps {
                sh 'npm init'
            }
        }         
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                sh './jenkins/scripts/kill.sh' 
            }
        }
    }
}
