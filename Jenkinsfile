pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''cd rails-mysql-docker
/usr/local/bin/docker-compose up -d'''
      }
    }
  }
}