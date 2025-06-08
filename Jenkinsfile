pipeline {
  agent any

  tools {
    nodejs 'NodeJS'
  }

  environment {
    NODE_ENV = 'development'
  }

  stages {
    stage('Clone Repository') {
      steps {
        echo 'Cloning repository...'
        checkout scm
      }
    }

    stage('Install Dependencies') {
      steps {
        echo 'Installing dependencies...'
        sh 'npm install'
      }
    }

      stage('Run Tests') {
      steps {
        echo 'Running tests...'
        sh 'npm test'
      }
    }

    stage('Build') {
      steps {
        echo 'Building the app...'
        sh 'npm run build'
      }
    }
  }

  post {
    success {
      echo 'Pipeline executed successfully.'
    }
    failure {
      echo 'Pipeline failed.'
    }
  }
}
