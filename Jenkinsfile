pipeline {
  agent any
  stages {
    stage('check out') {
      steps {
        checkout scm
      }
    }

    stage('docker compose stop') {
      steps {
        sh 'sudo docker-compose down'
      }
    }

    stage('docker compose start') {
      steps {
        sh 'sudo docker-compose up -d'
      }
    }

  }
  post {
    aborted {
      echo 'ABORTED'
    }

    success {
      echo 'SUCCESS'
    }

    failure {
      echo 'FAILURE'
    }

    changed {
      echo 'FAILURE'
    }

  }
}