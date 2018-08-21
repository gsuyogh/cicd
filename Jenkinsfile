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
        nexusPublisher nexusInstanceId: 'nexusserver', nexusRepositoryId: 'WintrustRepo', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'buildJob\\target\\cicd-1.0.0-mule-application.jar']], mavenCoordinate: [artifactId: 'cicd-jar', groupId: 'win.middleware.main', packaging: 'jar', version: '1.0']]]
      }
    }
 }
}
