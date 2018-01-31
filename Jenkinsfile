pipeline {
    agent any
    environment {
        ENV_NAME = "${env.BRANCH_NAME}"
        mvnHome = tool 'Maven'
    }
    tools {
        maven 'Maven'
        jdk 'jdk8u121'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh 'echo "PATH = ${PATH}"'
            }
        }

        stage ('Build') {
            steps {
                echo 'Building Branch: ' + env.BRANCH_NAME
                echo 'Build Number: ' + env.BUILD_NUMBER
                echo 'Building Environment: ' + ENV_NAME
               // def mvnHome = tool 'Maven'
                sh "${mvnHome}/bin/mvn clean install"
            }
         }
    }
}
