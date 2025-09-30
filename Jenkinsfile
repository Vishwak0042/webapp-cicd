pipeline {
    agent any

    environment {
        // Add environment variables if needed
        NODE_HOME = '/usr/local/bin/node' // adjust if Node is installed elsewhere
        PATH = "${env.NODE_HOME}:${env.PATH}"
    }

    stages {

        stage('Checkout SCM') {
            steps {
                git(
                    url: 'https://github.com/Vishwak0042/webapp-cicd.git',
                    branch: 'main',
                    credentialsId: 'github-pat' // Replace with your Jenkins credential ID
                )
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'npm run build' // Adjust if your project uses a different build command
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test' // Adjust based on your test command
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Example: Copy files to deployment folder or trigger deployment script
                sh 'cp -r ./dist /var/www/html/myapp' // Adjust path as per your server
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs for details.'
        }
    }
}
