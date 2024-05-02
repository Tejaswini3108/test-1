pipeline {
    agent {
        docker {
            // Specify the Docker image to use, which includes Python
            image 'python:3.9'
            // Define additional Docker arguments if needed
            args '-u root' // This might be necessary to run as root, depending on the Docker image
        }
    }
    
    stages {
        stage('Build') {
            steps {
                // Checkout the source code from your Git repository
                checkout scm
                
                // Install project dependencies
                sh 'pip install -r requirements.txt'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests
                sh 'python test.py'
            }
        }
    }
    
    post {
        always {
            // Cleanup steps that should always be executed
        }
        success {
            // Steps to execute when the pipeline is successful
        }
        failure {
            // Steps to execute when the pipeline fails
        }
    }
}
