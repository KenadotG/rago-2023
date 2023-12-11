pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout([$class: 'GitSCM', 
          branches: [[name: '*/main']], 
          userRemoteConfigs: [[url: 'https://github.com/KenadotG/rago-2023.git']]])
      }
    }

    stage('Build Docker Image') {
      steps {
        script {
          sh 'docker build -t nuxt-image .'
        }
      }
    }

    stage('Deploy to Minikube') {
      steps {
        script {
          sh 'kubectl apply -f nuxt-deployment.yaml'
        }
      }  
    }
  }
}