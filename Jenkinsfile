pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Vishwak0042/webapp-cicd.git',
                credentialsId: 'github-pat',
                branch: 'main'

            }
        }

        stage('Build') {
            steps {
                echo 'Building the app...'
                // for Node.js: sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // for Node.js: sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying to server...'
                // Example: sh 'scp index.html user@server:/var/www/html/'
            }
        }
    }
}
