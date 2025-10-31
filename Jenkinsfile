pipeline {
    agent any
    tools {
        nodejs 'NodeJS_20'  // NodeJS installation configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo "Building project..."
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying project..."
                // Example: scp to server
            }
        }
    }
}

