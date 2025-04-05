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
                // Use "python" if that's what is installed on your agent.
                sh 'python -m pip install -r requirements.txt'
            }
        }
        stage('Run Flask App') {
            steps {
                // Start the app in the background.
                sh 'nohup python app.py &'
            }
        }
    }
}
