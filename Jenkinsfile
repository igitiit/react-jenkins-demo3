pipeline {
    agent any
    
    tools {
        nodejs 'Node25'   // Make sure this matches your Jenkins NodeJS tool name
    }
    
    environment {
        CI = 'true'
    }
    
    stages {

        stage('Build') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                // Prevent failure when no tests exist
                bat 'npm test -- --watchAll=false --passWithNoTests'
            }
        }

        stage('Build Production') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo Deploying to production server'
                // Add real deployment commands here
            }
        }
    }
}
