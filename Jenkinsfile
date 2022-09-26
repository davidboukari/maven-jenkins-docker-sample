

pipeline {
  agent any
  tools {
    maven 'mymaven-3.8.6' 
  }
/*
    agent {
        docker { image 'maven:3.8.6-jdk-11' }
    }
*/
  stages {
    stage('Build and Install') {
      environment{
        USER_CREDS = credentials('devopsschool-nexus')
      }

      steps { 
       // withMaven(maven : 'mymaven-3.8.6') {
          sh 'mvn -s settings-jenkins.xml clean install -U -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true -Dmaven.wagon.http.ssl.ignore.validity.dates=true'
	//}
		
      }
    }
  }
}
