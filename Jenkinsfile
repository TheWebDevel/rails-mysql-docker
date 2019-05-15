pipeline {
  agent {
    node {
      label 'docker_rails'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '/usr/bin/docker-compose up -d'
      }
    }
  }
}