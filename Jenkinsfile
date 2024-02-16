pipeline {
  agent {
    label "worker-01"
  }
  /*environment {
    SECRET_VAR = credentials('secret_text')
    DOCKER_HUB = credentials('docker_creds')
  }*/
  stages {
    stage('Clean') {
      steps{
        sh 'echo "my hook works!"'
      }
    }
    /*stage('Build') {
      steps{
        sh 'docker build -t ashqa/nginx-custom .'
      }
    }
    stage('Deploy') {
      steps{
        sh 'docker run -d -p 80:80 --name nginx --mount type=bind,source=${WORKSPACE}/nginx.conf,target=/etc/nginx/nginx.conf ashqa/nginx-custom'
        sh 'echo ${SECRET_VAR}'
      }
    }
    stage('Test') {
      steps{
        sh 'sleep 5'
        sh 'curl localhost'
      }
    }
    stage('Update Registry') {
      steps {
        sh 'docker login --username="${DOCKER_HUB_USR}" --password="${DOCKER_HUB_PSW}"'
        sh 'docker push ashqa/nginx-custom'
      }
    }*/
  }
}