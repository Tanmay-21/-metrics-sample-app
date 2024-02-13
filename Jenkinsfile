pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building Application...'
        sh 'pip install -r requirements.txt'
        sh 'python -m unittest'
      }
    }
    stage('Build Docker Image') {
      steps {
        script {
          docker.build("metrics-sample-app-image")
        }
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
