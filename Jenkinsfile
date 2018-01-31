pipeline {
    agent any
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
                def mvnHome = tool 'Maven'
                sh "${mvnHome}/bin/mvn clean install"
            }
            //post {
             //   success {
                    //junit 'target/surefire-reports/**/*.xml' 
             //   }
           // }
        }
    }
}
