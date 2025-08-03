pipeline {
  agent any
 stages {
    stage('Clone Repository'){
        steps {
            git 'https://github.com/sh1shch1l1t/jenkins-docker-demo.git'
    
        }
    }

    stage('Build Docker Image'){
        steps {
            script {
                sh 'docker build -t jenkins-docker-demo .'
            }
        }
    }
    stage('RUN Docker Container'){
        steps {
            script {
                sh 'docker run -d -p 5000:5000 jenkins-docker-demo'
            }
        }

    }
 } 


}