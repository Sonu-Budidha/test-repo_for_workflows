pipeline {
    agent {
        docker {
            image 'node:20'
            args '-u root:root -v $WORKSPACE:$WORKSPACE'
            reuseNode true
        }
    }

    environment {
        NODE_ENV = 'development'
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out source code..."
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "Installing npm dependencies..."
                sh 'ls -la' // DEBUG: check if package.json exists
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo "Building the project..."
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
                echo "Deploying application..."
                // Add deployment commands here
            }
        }
    }

    post {
        success {
            echo "🎉 Pipeline completed successfully!"
        }
        failure {
            echo "❌ Pipeline failed. Check the logs for errors."
        }
        always {
            echo "🔹 Pipeline finished at ${new Date()}"
        }
    }
}

