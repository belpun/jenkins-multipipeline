
String testValue = "hellow world";


configFileProvider([configFile(fileId: "autoDeployProperties", variable: 'branch')]) {
   print 'printing branch name';
   print brach;
}

pipeline {
    agent any
	triggers { upstream(upstreamProjects: 'jenkins-multipipeline-trigger/trigger', threshold: hudson.model.Result.SUCCESS) }
    stages {
        stage("build-and-deploy-dev") {
            when {
                branch "main"
            }
            steps {
				
				echo "${testValue}";
                powershell "mvn clean test";
            }
        }
    }
}
