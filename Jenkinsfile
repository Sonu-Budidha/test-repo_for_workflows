pipeline {
    agent any

    environment {
        APP_DIR = "my-app"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out source code..."
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building the project..."
                // If Node.js project, example:
                sh 'npm install'
                sh 'npm run build'  // or just copy files if static site
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                // Example test command for Node.js or Python
                sh 'npm test || true' // or pytest
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying project to server..."
                // Example: copy files to web server
                sh 'scp -r ./dist/* user@yourserver:/var/www/html/'
                echo "Project deployed! Visit: http://yourserver/"
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully! Project is live.'
        }
        failure {
            echo 'Pipeline failed! Check logs.'
        }
    }
}

