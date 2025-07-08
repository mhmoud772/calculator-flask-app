pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/mhmoud772/calculator-flask-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run App') {
            steps {
                sh '''
                pkill -f app.py || true
                nohup python3 app.py > output.log 2>&1 &
                '''
            }
        }
    }
}