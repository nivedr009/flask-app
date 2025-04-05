pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out from the configured SCM
                checkout scm
            }
        }
        stage('Install Dependencies and Run Flask App') {
            steps {
                script {
                    // Run inside the official Python 3.9 image
                    docker.image('python:3.9').inside {
                        // Install dependencies
                        sh 'pip install -r requirements.txt'
                        // Start the Flask app in the background
                        sh 'nohup flask run --host=0.0.0.0 --port=5000 &'
                        // Optional: sleep for a short period to allow the app to start
                        sh 'sleep 5'
                    }
                }
            }
        }
    }
}
