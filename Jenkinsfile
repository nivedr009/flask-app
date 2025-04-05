pipeline {
    agent {
        docker { image 'jenkins-python' }
    }
    stages {
        stage('Checkout Code') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/nivedr009/flask-app.git',
                        credentialsId: 'flaskid'
                    ]]
                ])
            }
        }
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
