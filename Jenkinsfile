pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/nivedr009/flask-app.git'
            }
        }
        stage('Install Dependencies and Run Flask App') {
            steps {
                script {
                    docker.image('python:3.9').inside {
                        sh 'pip install -r requirements.txt'
                        sh 'nohup python app.py &'
                    }
                }
            }
        }
    }
}
