pipeline {
    agent {
        docker {
            image 'node:chandra111/react-node-image' 
            args '-p 3000:3000' 
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
