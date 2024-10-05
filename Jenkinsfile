pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('Checkout') {
	    steps {
		    sh git URL: 'https://github.com/gideonisele/devsecops-jenkins-k8s-tf-sast-sonarcloud-repo.git'
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
