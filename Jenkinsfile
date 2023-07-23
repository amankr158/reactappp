pipeline {
    agent any // This pipeline can run on any available agent

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the GitHub repository
                git 'https://github.com/amankr158/reactappp'
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
}
