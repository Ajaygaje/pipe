pipeline {
    agent any
    stages {
        stage("Setup Environment") {
            steps {
                bat '''
                choco install nodejs -y || echo "Node.js already installed"
                node --version
                npm --version
                npm install
                '''
            }
        }
        stage("Test") {
            steps {
                bat 'npm test'
            }
        }
        stage("Build") {
            steps {
                bat 'npm run build'
            }
        }
        stage("Deploy") {
            steps {
                echo 'Deploying application...'
            }
        }
    }
}
