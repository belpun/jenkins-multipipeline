
String testValue = "hellow world";



pipeline {


    agent any
	triggers { upstream(upstreamProjects: 'jenkins-multipipeline-trigger/trigger', threshold: hudson.model.Result.SUCCESS) }
    stages {
        stage("build-and-deploy-dev") {
		
			configFileProvider([configFile(fileId: "b137218d-3dab-471a-b8db-ca94e52e7072", variable: 'autoDeployProperties')]) {
				echo 'testing values'
			}
            when {
                branch "main"
            }
            steps {
				
				
                powershell "mvn clean test";
            }
        }
    }
}
