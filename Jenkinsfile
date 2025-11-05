pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'docker build -t deepzz72206/getting-started-app:latest .'
      }
    }
    stage('Push to DockerHub') {
      steps {
        sh 'docker login -u deepzz72206 -p qwerty123'
        sh 'docker push deepzz72206/getting-started-app:latest'
      }
    }
    stage('Deploy to Kubernetes') {
      steps {
        sh 'kubectl apply -f my-kube1-deployment.yaml'
        sh 'kubectl apply -f my-kube1-service.yaml'
      }
    }
  }
}
