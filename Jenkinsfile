pipeline {
  agent {
    node {
      label 'api-test'
    }

  }
  stages {
    stage('source') {
      steps {
        sh '''auth="viera_token"

echo "${auth}"'''
      }
    }

  }
}