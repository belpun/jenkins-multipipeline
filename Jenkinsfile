pipeline {
    agent any
	triggers { upstream(upstreamProjects: 'jenkins-multipipeline-trigger/trigger', threshold: hudson.model.Result.SUCCESS) }
    stages {
        stage("build-and-deploy-dev") {
            when {
                branch "main"
            }
            steps {
				String testValue = "hellow world";
				echo "${testValue}";
                powershell "mvn clean test";
            }
        }
    }
}
