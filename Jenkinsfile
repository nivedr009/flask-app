pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/nivedr009/flask-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m pip install -r requirements.txt'
            }
        }

        stage('Run Flask App') {
            steps {
                sh 'nohup python3 app.py &'
            }
        }
    }
}
