pipeline {
  agent any
  stages {
    stage('Building image') {
      steps {
        sh 'docker-compose build'
      }
    }
    stage('Deploy Image') {
      steps {
        script {
          websiteImage = "rails-mysql-docker_master_website" + ":$BUILD_NUMBER"
          sidekiqImage = "rails-mysql-docker_master_sidekiq" + ":$BUILD_NUMBER"
          docker.withRegistry( '', registryCredential ) {
            websiteImage.push()
            sidekiqImage.push()
          }
        }

      }
    }
    stage('Remove Unused docker image') {
      steps {
        sh "docker rmi $websiteImage:$BUILD_NUMBER"
        sh "docker rmi $sidekiqImage:$BUILD_NUMBER"
      }
    }
  }
  environment {
    registry = 'sathishcodes/sample'
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
}