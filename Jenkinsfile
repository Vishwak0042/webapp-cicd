
pipeline { 
    agent any 
 
    stages { 
        stage('Checkout') { 
            steps { 
                git(
                    url: 'https://github.com/Vishwak0042/webapp-cicd.git',
                    branch: 'main',
                    credentialsId: 'github-pat' // Replace with your Jenkins credential ID
                ) 
            } 
        } 
 
        stage('Build') { 
            steps { 
                echo 'Building the app...' 
                // npm install or other build commands 
            } 
        } 
 
        stage('Test') { 
            steps { 
                echo 'Running tests...' 
                // npm test or pytest etc. 
            } 
        } 
 
        stage('Deploy') { 
            steps { 
                echo 'Deploying to server...' 
                // docker build, docker push or scp to deploy 
            } 
        } 
    } 
}