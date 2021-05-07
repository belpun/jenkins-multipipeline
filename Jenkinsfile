
String testValue = "hellow world";



pipeline {


    agent any
	 parameters
  {
    string(name: 'BRANCH_PASSED_OVER', defaultValue: '${env.BRANCH_NAME}', description: 'pass branch value')
    string(name: 'PERSON2', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
  }
	triggers { upstream(upstreamProjects: 'jenkins-multipipeline-trigger/trigger', threshold: hudson.model.Result.SUCCESS) }
    stages {
        stage("build-and-deploy-dev") {
		
		          when {
                branch "main"
            }
            steps {
				
				
                powershell "mvn clean test";
            }
        }
    }
}
