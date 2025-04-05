pipeline {
    agent {
        docker {
            image 'python:3.9'
        }
    }

    stages {
        stage('Install Requirements') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Flask App') {
            steps {
                sh 'flask run --host=0.0.0.0 --port=5000'
            }
        }
    }
}
