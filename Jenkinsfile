
String testValue = "hellow world";

pipeline {
    agent any
	triggers { upstream(upstreamProjects: 'jenkins-multipipeline-trigger/trigger', threshold: hudson.model.Result.SUCCESS) }
    stages {
        stage("build-and-deploy-dev") {
            when {
                branch "main"
            }
            steps {
				configFileProvider([configFile(fileId: "autoDeployProperties", variable: 'branch')]) {
				   print 'printing branch name';
				   print brach;
				}
				echo "${testValue}";
                powershell "mvn clean test";
            }
        }
    }
}
