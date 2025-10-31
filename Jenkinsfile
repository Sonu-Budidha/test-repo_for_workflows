pipeline {
    agent {
        docker {
            image 'node:20'
            args '-u root:root'
        }
    }
    stages {
        stage('Checkout') { steps { checkout scm } }
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Test') { steps { sh 'npm test' } }
        stage('Deploy') { steps { echo 'Deploying...' } }
    }
}

