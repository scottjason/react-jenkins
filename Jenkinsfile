pipeline {
    agent { label 'dockerserver' } // if you don't have other steps, 'any' agent works
    stages {
        stage('Build') {
            agent {
              docker {
                label 'dockerserver'  // both label and image
                image 'node:10.19.0-slim'
                args '-p 3000:3000'
              }
            }
            steps {
                sh 'npm install'
            }
        }
    }
}
