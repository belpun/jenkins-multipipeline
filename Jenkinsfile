
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
				configFileProvider([configFile(fileId: "b137218d-3dab-471a-b8db-ca94e52e7072", variable: 'branch')]) {
				   print 'printing branch name';
				   print branch;
				   print 'printing branch name with dollar sign';
				   echo "${branch}";
				}
				
                powershell "mvn clean test";
            }
        }
    }
}
