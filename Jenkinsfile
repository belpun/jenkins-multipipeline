pipeline {
    agent any
    stages {
        stage("build-and-deploy-dev") {
            when {
                branch "main"
            }
            steps {
                powershell "mvn -U clean package -DskipTests -DskipITs"
                archiveArtifacts artifacts: '**/target/*.zip,**/target/bita-server/*.zip', fingerprint: true
                withCredentials([usernamePassword(credentialsId: 'bpundomain', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    echo "Deploying to bita-dev1-app"
					// uncomment this line if you want to deploy the latest changes. 
                    // powershell './devops/deploy.ps1 "BITA-CLIENT-09" "E:\\bita"'
                }
            }
        }
    }
}
