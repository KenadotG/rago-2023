pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/KenadotG/rago-2023.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        script {
          docker.build('kenag/nuxt-project')
        }
      }
    }

    stage('Deploy to Minikube') {
      steps {
        sh 'kubectl apply -f nuxt-deployment.yaml'
      }
    }
  }
}