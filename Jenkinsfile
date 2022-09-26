

pipeline {
  agent any
/*
    agent {
        docker { image 'maven:3.8.6-jdk-11' }
    }
*/
  stages {
    environment{
        USER_CREDS = credentials('devopsschool-nexus')
    }


    stage('Build and Install') {
      steps {
        sh 'mvn -s settings-jenkins.xml clean install -U -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true -Dmaven.wagon.http.ssl.ignore.validity.dates=true'
      }
    }
  }
}
