pipeline {
  agent any
  stages {
    stage('auth_token') {
      steps {
        sh '''auth="$(curl -X POST \\
    http://192.168.179.38:28080/proauth/oauth/Authenticate \\
    -H \'Content-Type: application/json\' \\
    -d \'{"dto":
            {
                "user_id": "admin",
                "password": "admin"
            }
        }\')"


auth_token=$(echo "$auth" | cut -d \':\' -f5 | cut -d \'"\' -f2)

echo "$auth_token"'''
      }
    }

    stage('check_env') {
      steps {
        sh 'echo "${auth_token}"'
      }
    }

  }
  environment {
    auth_token = '$auth_token'
  }
}