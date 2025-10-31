pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building application...'
        sh 'mvn clean package'
      }
    }
    stage('Test') {
      steps {
        echo 'Running tests...'
        sh 'mvn test'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying to server...'
      }
    }
  }
}
