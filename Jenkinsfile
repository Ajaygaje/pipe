pipeline {
    agent any
    tools {
        nodejs "NodeJS" // Use the name configured in Jenkins
    }
    stages {
        stage("Checkout") {
            steps {
                checkout scm
            }
        }
        stage("Setup Environment") {
            steps {
                script {
                    bat 'node --version'
                    bat 'npm --version'
                    bat 'npm install'
                }
            }
        }
        stage("Test") {
            steps {
                script {
                    bat 'npm test'
                }
            }
        }
        stage("Build") {
            steps {
                script {
                    bat 'npm run build'
                }
            }
        }
        stage("Deploy") {
            steps {
                script {
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
