pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/faraday-academy/curriculum-app', branch: 'dev')
      }
    }

    stage('Log') {
      steps {
        sh 'ls -la'
      }
    }

    stage('Log into Dockerhub') {
      environment {
        DOCKERHUB_USER = 'Ozone183'
        DOCKERHUB_PASSWORD = 'Quebec01queue#'
      }
      steps {
        sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
        sh 'uname '
      }
    }

    stage('Push') {
      steps {
        sh 'docker push fuze365/curriculum-front:latest'
      }
    }

    stage('List the username') {
      steps {
        sh 'uname'
      }
    }

  }
  environment {
    DOCKERHUB_USER = 'Ozone183'
    DOCKERHUB_PASSWORD = 'Quebec01queue#'
  }
}