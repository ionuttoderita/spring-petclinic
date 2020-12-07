// Powered by Infostretch 

timestamps {

node () {

	stage ('spring-petclinic - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '254a3de3-6377-4c29-b093-fa11430d4d27', url: 'https://github.com/ionuttoderita/spring-petclinic.git']]]) 
	}
	stage ('spring-petclinic - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.timestamper.TimestamperBuildWrapper". Please verify and convert manually if required.		// Shell build step
sh """ 
./mvnw package 
 """
		archiveArtifacts allowEmptyArchive: false, artifacts: 'target/spring-petclinic-2.4.0.BUILD-SNAPSHOT.jar', caseSensitive: true, defaultExcludes: true, fingerprint: false, onlyIfSuccessful: false
		// JUnit Results
		junit 'target/surefire-reports/*.xml' 
	}
}
}