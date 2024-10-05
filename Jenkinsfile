pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asesgurubuggywebapp -Dsonar.organization=asesgurubuggywebapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=d75deaf7125ae87e73c0f48aa17563f0c697c8e3'
			}
        } 
  }
}
