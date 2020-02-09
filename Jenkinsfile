#!groovy

pipeline {
    agent {
        any {
            image 'node:10.19.0-slim'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build App') {
            steps {
                sh 'npm install'
            }
        }
    }
}