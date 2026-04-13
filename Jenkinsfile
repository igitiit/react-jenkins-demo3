pipeline {
    agent any
    
    tools {
        nodejs 'Node25'   // Make sure this matches your Jenkins NodeJS tool name
    }
    
    environment {
        CI = 'true'
        nodejs "Node25"   // Make sure you configured a NodeJS tool in Jenkins named "NodeJS"

    }
    
    stages {

        stage('Build') {
            steps {
                bat 'npm install'
                checkout scm
            }
        }

        stage('Test') {
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
                bat 'echo Deploying to production server'
                // Add real deployment commands here
            }
        }
    }
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
}
