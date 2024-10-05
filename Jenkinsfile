pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
	stage('Checkout') {
	   steps {
		git branch: 'main', url: 'https://github.com/gideonisele/devsecops-jenkins-k8s-tf-sast-sonarcloud-repo.git'   
	   }
	}
    stage('Build') {
	    steps {
		    sh 'mvn clean install'
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
