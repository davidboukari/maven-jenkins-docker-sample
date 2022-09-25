
environment{
    USER_CREDS = credentials('devopsschool-nexus')
}


pipeline {
    agent {
        docker { image 'maven:3.8.6-jdk-11' }
    }
    stages {
        stage('Build and Install') {
            steps {
                sh 'mvn -s settings-jenkins.xml clean install'
            }
        }
    }
}
