pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }
    
  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'npm install'
            sh 'npm install'
          }
        }
        stage('build-test') {
          steps {
            sh 'npm install'
          }
        }
      }
    }
  }
}