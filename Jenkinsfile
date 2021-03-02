pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
      }
    }

    stage('stop node docker') {
      steps {
        sh '(docker rm -f node-docker-sample_main_server_1 | true) && docker-compose up -d server '
      }
    }

    stage('start docker') {
      steps {
        sh 'docker-compose up -d server '
      }
    }

  }
}