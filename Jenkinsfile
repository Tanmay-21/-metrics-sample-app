pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building Application...'
      }
    }
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t metrics-app-image .'
      }
    }
    stage('Deploy to Kubernetes') {
      steps {
        sh 'kubectl apply -f deployment.yaml'
        sh 'kubectl apply -f service.yaml'
      }
    }
  }
}
