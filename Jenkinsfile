
pipeline {
    agent any

    tools {
        nodejs "Node25"   // Make sure you configured a NodeJS tool in Jenkins named "NodeJS"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                // Prevent failure if no tests exist
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
                echo "Deploy step goes here"
                // Example:
                // bat 'xcopy /E /I build C:\\inetpub\\wwwroot\\myapp'
            }
        }
    }

    post {
        success {
            echo "Build completed successfully!"
        }
        failure {
            echo "Build failed."
        }
    }
}
