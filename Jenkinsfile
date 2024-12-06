// Jenkinsfile
pipeline {
    agent any

    environment {
        NODE_HOME = tool name: 'NodeJS', type: 'NodeJS'
        PATH = "${NODE_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the Git repository
                git 'https://github.com/Arsh-Alam1/node.js.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                // Run tests (optional step, can be skipped if no tests)
                sh 'npm test'
            }
        }
        stage('Build') {
            steps {
                // Build the application (optional)
                sh 'npm run build'  // This is if you have a build script
            }
        }
        stage('Deploy') {
            steps {
                // Deploy the application (or echo for testing)
                echo 'Deploying Node.js application'
            }
        }
    }

    post {
        always {
            // Clean up, if needed
            echo 'Cleaning up'
        }
    }
}
