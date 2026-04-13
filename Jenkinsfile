pipeline {
    agent any

    tools {
<<<<<<< HEAD
        nodejs "Node25"   // Make sure you configured a NodeJS tool in Jenkins named "NodeJS"
=======
        nodejs 'Node25'
    }

    environment {
        CI = 'true'
>>>>>>> 32f1a5efa8b02ced34a47bad6f97b0ec37d85cdd
    }

    stages {

        stage('Checkout') {
            steps {
<<<<<<< HEAD
                checkout scm
=======
                bat 'npm install'
>>>>>>> 32f1a5efa8b02ced34a47bad6f97b0ec37d85cdd
            }
        }

        stage('Install Dependencies') {
            steps {
<<<<<<< HEAD
                bat 'npm install'
=======
                bat 'npm test -- --watchAll=false'
>>>>>>> 32f1a5efa8b02ced34a47bad6f97b0ec37d85cdd
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
<<<<<<< HEAD
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
=======
                bat 'echo Deploying to production server'
            }
        }
    }
>>>>>>> 32f1a5efa8b02ced34a47bad6f97b0ec37d85cdd
}
