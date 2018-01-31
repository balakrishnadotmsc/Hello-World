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
                def pom = readMavenPom file: 'pom.xml'
                def version = pom.version.replace("-SNAPSHOT", ".${currentBuild.number}")
                sh "${mvnHome}/bin/mvn -DreleaseVersion=${version} -DdevelopmentVersion=${pom.version} -DpushChanges=false -DlocalCheckout=true -DpreparationGoals=initialize release:prepare release:perform -B"
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
