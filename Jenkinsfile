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
          agent {
            docker {
              image 'node:6-alpine'
              args '-p 3000:3000'
            }
            
          }
          steps {
            sh 'npm install'
          }
        }
      }
    }
  }
}