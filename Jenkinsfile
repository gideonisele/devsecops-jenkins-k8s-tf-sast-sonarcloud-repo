pipeline {
  agent any
  tools { 
        maven 'Maven_3_6_3'  
    }
   stages{
    stage('Checkout') {
	    steps {
		   git url: 'https://github.com/gideonisele/devsecops-jenkins-k8s-tf-sast-sonarcloud-repo.git',
			   branch: 'main'
	    }
    }
    stage('Build') {
	    steps {
		    sh 'mvn install'
	    }
    }
    stage('Test') {
	    steps {
		    sh 'mvn test'
	    }
    } 
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asgbuggywebapp -Dsonar.organization=asgbuggywebapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=9325586a8f1d1adf470b908a46156f5844'
			}
        } 
  }
}
