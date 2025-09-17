pipeline {
    agent any
    stages {
        stage('Install dependencies') {
            steps {
                sh 'python -m pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'python -m pytest'
            }
        }
    }
}
