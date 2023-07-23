pipeline {
    agent any // This pipeline can run on any available agent

    stages {
        stage('Install dependencies') {
            steps {
                // Install Node.js and npm if not already installed
                sh 'node --version'

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
