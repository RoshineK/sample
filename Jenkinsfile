node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/RoshineK/sample.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '66f658d6-36e9-4be9-8728-2a47c314a991', snykInstallation: 'snyknew', snykTokenId: 'snykkey'
       
   }

}
