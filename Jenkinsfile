pipeline {
  agent {
    docker {
      image 'docker:20.10.16-dind'
      args '-v /var/run/docker.sock:/var/run/docker.sock'
    }
  }

  stages {
    stage('Clone Repository') {
      steps {
        git 'https://github.com/sh1shch1l1t/jenkins-docker-demo.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t jenkins-docker-demo .'
      }
    }

    stage('Run Docker Container') {
      steps {
        sh 'docker run -d -p 5000:5000 jenkins-docker-demo'
      }
    }
  }
}