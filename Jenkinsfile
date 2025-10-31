 pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building the project..."
                sh 'echo "Build complete!"'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'echo "All tests passed!"'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
    }
}
