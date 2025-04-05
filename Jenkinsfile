pipeline {
    agent {
        docker { image 'python:3.9' }
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run Flask App') {
            steps {
                sh 'python app.py'
            }
        }
    }
}
