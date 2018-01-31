pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'npm install'
          }
        }
        stage('build-test') {
          agent any
          steps {
            sh 'npm install'
          }
        }
      }
    }
  }
}