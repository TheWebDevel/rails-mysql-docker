pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '/usr/bin/docker-compose up -d'
      }
    }
  }
}