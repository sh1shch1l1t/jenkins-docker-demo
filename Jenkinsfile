pipeline {
  agent {
    docker {
      image 'docker:20.10.16'  // официальный образ с докером внутри
      args '-v /var/run/docker.sock:/var/run/docker.sock' // проброс сокета Docker хоста
    }
  }

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