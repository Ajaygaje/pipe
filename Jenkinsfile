pipeline {
    agent any 
    tools {
        nodejs "NodeJS" // Ensure Node.js is installed via Jenkins Tools
    }
    stages {
        stage("Checkout") {
            steps {
                // Checkout code from the source control management system
                checkout scm
            }
        }
        stage("Setup Environment") {
            steps {
                script {
                    // Verify Node.js and npm installation
                    bat 'node --version'
                    bat 'npm --version'

                    // Install project dependencies
                    bat 'npm install'
                }
            }
        }
        stage("Test") {
            steps {
                script {
                    // Run tests defined in the package.json
                    bat 'npm test'
                }
            }
        }
        stage("Build") {
            steps {
                script {
                    // Build the project (adjust the script as needed for your project)
                    bat 'npm run build'
                }
            }
        }
        stage("Deploy") {
            steps {
                script {
                    // Deploy the application (customize as per your requirements)
                    echo 'Deploying application...'
                }
            }
        }
    }
    post {
        always {
            echo "Pipeline execution complete."
        }
        success {
            echo "Pipeline succeeded!"
        }
        failure {
            echo "Pipeline failed. Check the logs for details."
        }
    }
}
