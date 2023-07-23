pipeline {
    agent any // This pipeline can run on any available agent

    stages {
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
