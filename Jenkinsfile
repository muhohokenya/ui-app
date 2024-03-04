pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checks out your Vue.js project from a source control management system like Git
                checkout scm
            }
        }

        stage('Install dependencies') {
            steps {
                // Use Node's package manager to install dependencies
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Test') {
            steps {
                // Run your tests. Could be unit tests, linting, etc.
                script {
                    sh 'npm run test:unit'
                }
            }
        }

        stage('Build') {
            steps {
                // Build your Vue.js application for production
                script {
                    sh 'npm run build'
                }
            }
        }

        // Optional: Add additional stages for deployment if needed
        stage('Deploy') {
            steps {
                // Deployment steps go here
                // For example, you could use SCP or SSH to transfer build artifacts to a server
                echo 'Deploying application...'
                // sh 'scp -r dist/ user@your-server:path/to/deploy'
            }
        }
    }

    post {
        always {
            // Clean up workspace after build/test/deploy
            cleanWs()
        }
        success {
            // Actions to take if pipeline succeeds
            echo 'Build and Test Stages Successful!'
        }
        failure {
            // Actions to take if pipeline fails
            echo 'An error has occurred.'
        }
    }
}
