pipeline {
  agent any
  environment {
     ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
  }
  stages {
 	stage ('Build'){
 		steps {
 			
 				bat 'mvn -f pom.xml clean install'
 			
 		}
 	}
 	stage ('Deploy'){
 		steps {
 		
 				bat 'mvn -f pom.xml package deploy  -Dusername=$ANYPOINT_USR -Dpassword=$ANYPOINT_PSW -Denvironment=Development -DmuleDeploy'
 			
 		}
 	}
 }
}
