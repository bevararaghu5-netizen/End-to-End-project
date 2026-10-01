pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/bevararaghu5-netizen/End-to-End-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat '''
                    echo ===== DOCKER VERSION =====
                    docker --version

                    echo ===== BUILDING DOCKER IMAGE =====
                    docker build -t devops-web:1.0 .

                    if %ERRORLEVEL% NEQ 0 exit /b %ERRORLEVEL%

                    echo ===== DOCKER IMAGES =====
                    docker images
                '''
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat '''
                    echo ===== KUBECTL VERSION =====
                    kubectl version --client

                    echo ===== KUBERNETES CONTEXT =====
                    kubectl config current-context

                    echo ===== KUBERNETES NODES =====
                    kubectl get nodes

                    echo ===== APPLYING KUBERNETES FILES =====
                    kubectl apply -f k8s/

                    echo ===== KUBERNETES DEPLOYMENT =====
                    kubectl get deployments

                    echo ===== KUBERNETES PODS =====
                    kubectl get pods

                    echo ===== KUBERNETES SERVICES =====
                    kubectl get services
                '''
            }
        }
    }
}