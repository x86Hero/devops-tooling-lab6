pipeline {
  agent {
    label "worker-01"
  }
  environment {
    SECRET_VAR = credentials('secret_text')
    DOCKER_HUB = credentials('docker_creds')
  }
  stages {
    stage('Clean') {
      steps{
        sh 'echo "my hook works!"'
        sh 'docker-compose --help'
      }
    }
    stage('Test') {
      steps{
        sh 'cd ${WORKSPACE}/Task1'
        sh 'docker-compose up -d'
      }
    /*stage('Update Registry') {
      steps {
        sh 'docker login --username="${DOCKER_HUB_USR}" --password="${DOCKER_HUB_PSW}"'
        sh 'docker push ashqa/nginx-custom'
      }
    }*/
    }
  }
}