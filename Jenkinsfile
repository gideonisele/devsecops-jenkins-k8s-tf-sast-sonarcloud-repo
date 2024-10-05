pipeline {
  agent any
  tools { 
        maven 'MAVEN3'  
    }
   stages{
	stage('Checkout') {
	   steps {
		git branch: 'main', url: 'https://github.com/gideonisele/devsecops-jenkins-k8s-tf-sast-sonarcloud-repo.git'   
	   }
	}
    stage('Test') {
	    steps {
		    sh 'mvn test'
	    }
    }
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=new-app-java-sast -Dsonar.organization=new-app-java-sast -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=50d6aedeb92bc2f370ce794a7a60580bede0ea99'
			}
        } 
  }
}
