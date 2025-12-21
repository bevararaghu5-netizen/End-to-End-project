pipeline {
  agent any
  stages {
    stage('Clone Repo') {
      steps {
        git 'https://github.com/m-prasanna/devops-resume-project.git'
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
