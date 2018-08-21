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
    stage('Publish') {
    nexusPublisher nexusInstanceId: 'nexusserver', nexusRepositoryId: 'WintrustRepo', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'test\\target\\cicd-1.0.0-mule-application.jar']], mavenCoordinate: [artifactId: 'cicd-jar', groupId: 'win.middleware.main', packaging: 'jar', version: '1.0']]]
   }
 }
}
