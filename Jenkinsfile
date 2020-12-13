pipeline {
    agent any
    stages {
        stage("build-and-deploy-dev") {
            when {
                branch "main"
            }
            steps {
                powershell "mvn clean test"
            }
        }
    }
}
