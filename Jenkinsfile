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
 		
 				bat 'mvn -f pom.xml package deploy  -Dusername=mulesuyogh4 -Dpassword=Password123 -Denvironment=Development -DmuleDeploy'
 			
 		}
 	}
 }
}
