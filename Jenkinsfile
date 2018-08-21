pipeline {
  agent any  
  stages {
 	stage ('Build'){
 		steps {
 			
 				bat 'mvn -f pom.xml clean install'
 			
 		}
 	}
    
 	
    stage ('Publish') {
      steps {
        nexusPublisher nexusInstanceId: 'nexusserver', nexusRepositoryId: 'WintrustRepo', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'C:\\Windows\\system32\\config\\systemprofile\\.m2\\repository\\my\\app\\cicd\\1.0.0\\cicd-1.0.0-mule-application.jar']], mavenCoordinate: [artifactId: 'cicd-jar', groupId: 'win.middleware.main', packaging: 'jar', version: '2.0']]]
      }
    }
 }
}
