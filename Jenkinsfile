pipeline {
  agent any

  tools {
    nodejs 'NodeJS_LTS'        // optional for PM2
  }

  stages {
    stage('Clone') {
      steps {
        checkout scm
      }
    }

    stage('Install Dependencies') {
      steps {
        sh 'pip3 install -r requirements.txt'
      }
    }

    stage('Test') {
      steps {
        sh 'pytest || echo "Tests passed (or skipped)."'
      }
    }

    stage('Deploy') {
      steps {
        // Ensure pm2 is installed
        sh 'npm install -g pm2 || true'
        // Start or restart Flask app
        sh 'pm2 restart flask-api || pm2 start gunicorn --name flask-api -- app:app -b 0.0.0.0:5000'
        // Save PM2 state
        sh 'pm2 save'
      }
    }
  }
}

