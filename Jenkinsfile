#!groovy

pipeline {
    stage('Initialize'){
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }
    agent {
        docker {
            image 'node:10.19.0-slim'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
       stage('Build Docker'){
            steps {
              sh './dockerBuild.sh'
            }
       }
        stage('Build App') {
            steps {
                sh 'npm install'
            }
        }
    }
}



