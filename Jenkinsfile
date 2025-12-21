pipeline {
  agent any
  stages {
    stage('Clone Repo') {
      steps {
        git 'https://github.com/m-prasanna/End-to-End-DevOps-Pipeline-using-Docker-Jenkins-Kubernetes-Monitoring.git'
      }
    }
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t devops-web .'
      }
    }
    stage('Deploy to Kubernetes') {
      steps {
        sh 'kubectl apply -f k8s/'
      }
    }
  }
}
