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
        sh 'docker system prune -a -f || true'
        sh 'docker builder prune -a -f || true'
        sh 'docker rm -f $(docker ps -aq) || true'
        sh 'docker rmi -f $(docker images) || true'
      }
    }
    stage('Test') {
      steps{
        sh 'cd ${WORKSPACE}/Task1 && docker-compose up -d'
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