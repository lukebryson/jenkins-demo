pipeline {
  agent {
    docker {
      image 'python:3.11-slim'
      // optional: args '-u root' if you hit permission issues
    }
  }
  stages {
    stage('Install dependencies') {
      steps { sh 'python -m pip install -r requirements.txt' }
    }
    stage('Run Tests') {
      steps { sh 'pytest -q --junitxml=reports/tests.xml' }
    }
  }
  post {
    always {
      junit 'reports/tests.xml'   // requires JUnit plugin
    }
  }
}
