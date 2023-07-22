pipeline {
    agent any // This pipeline can run on any available agent

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the GitHub repository
                git 'https://github.com/yourusername/your-react-app.git'
            }
        }

        stage('Install dependencies') {
            steps {
                // Install Node.js and npm if not already installed
                sh 'curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -'
                sh 'sudo apt-get install -y nodejs'

                // Install project dependencies
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                // Build the React app
                sh 'npm run build'
            }
        }
    }

    post {
        success {
            // If the build is successful, you can perform additional actions here
            echo 'Build successful!'
        }
        failure {
            // If the build fails, you can perform actions here (e.g., send notifications)
            echo 'Build failed!'
        }
    }
}
