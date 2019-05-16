pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile'
    }

  }
  stages {
    stage('Build') {
      agent {
        dockerfile {
          filename 'Dockerfile'
        }

      }
      steps {
        git(url: 'https://github.com/TheWebDevel/rails-mysql-docker.git', credentialsId: 'fe9a0bca-6c2f-48d9-8876-6cc23e2a33c9	', branch: 'master')
      }
    }
  }
}