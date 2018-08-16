pipeline {
  agent any  
  stages {
 	stage ('Build'){
 		steps {
 			
 				bat 'mvn -f pom.xml clean install'
 			
 		}
 	}
 	stage ('Deploy'){
    environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
 		steps {
 		
      bat 'mvn -f pom.xml package deploy -Danypoint.username=%ANYPOINT_CREDENTIALS_USR% -Danypoint.password=%ANYPOINT_CREDENTIALS_PSW% -Denvironment=Development -DmuleDeploy'
 			
 		}
 	}
 }
}
