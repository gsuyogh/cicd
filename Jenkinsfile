pipeline {
  agent any
  environment {
     ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
  }
  stages {    
    stage('Build') {
      
      steps {
      
        bat 'mvn deploy -f pom.xml clean install'
        
      }
    }
    stage('Deploy CloudHub') {
      
      steps {
        
        bat 'mvn -f pom.xml package deploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW}'
        
      }
    }
  }
}
