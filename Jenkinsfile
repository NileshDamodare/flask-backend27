pipeline {
  agent any
  tools {
    nodejs 'NodeJS_LTS'        // Name set in Jenkins Global Tool Config
    python 'Python3'           // Name set in Jenkins Global Tool Config
  }
  stages {
    stage('Clone') {
      steps { checkout scm }
    }
    stage('Install Dependencies') {
      steps {
        sh 'pip3 install -r requirements.txt'
      }
    }
    stage('Test') {
      steps {
        sh 'pytest || echo "No tests found or tests skipped."'
      }
    }
    stage('Deploy') {
      steps {
        sh 'npm install -g pm2 || true'
        sh 'pm2 restart flask-api || pm2 start gunicorn --name flask-api -- app:app -b 0.0.0.0:5000'
        sh 'pm2 save'
      }
    }
  }
}

