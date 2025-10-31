pipeline {
    agent {
        docker {
            image 'node:20'
            args '-u root:root' // run as root inside the container
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
                // You can add actual deployment commands here
                // Example: sh 'scp -r dist user@server:/var/www/app'
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

