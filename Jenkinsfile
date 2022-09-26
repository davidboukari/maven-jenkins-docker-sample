

pipeline {
  agent any
  environment{
    USER_CREDS = credentials('devopsschool-nexus')
  }
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

      steps { 
          sh 'mvn -s settings-jenkins.xml clean install -U -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true -Dmaven.wagon.http.ssl.ignore.validity.dates=true'
      }
    }
  }
}


/*
pipeline {
  agent any
  tools {
    maven 'maven-3.6.3' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: 'tomcat_credential', path: '', url: 'http://dayal-test.letspractice.tk:8081')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' 
        }
      }
    }
  }
}
*/
