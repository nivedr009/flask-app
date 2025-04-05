pipeline {
    agent {
        docker {
            image 'python:3.9' // This runs the pipeline steps inside a Python environment
        }
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the repository'
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'pip install --upgrade pip'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Flask App') {
            steps {
                echo 'Starting Flask App...'
                sh 'flask run --host=0.0.0.0 --port=5000'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully'
        }
        failure {
            echo '❌ Pipeline failed'
        }
    }
}
