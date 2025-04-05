pipeline {
    agent {
        docker { image 'jenkins-python' }
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'python3 -m pip install -r requirements.txt'
            }
        }
        stage('Run Flask App') {
            steps {
                sh 'python3 app.py'
            }
        }
    }
}
