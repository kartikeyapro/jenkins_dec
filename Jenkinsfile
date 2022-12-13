pipeline {
    agent any

    tools {
          maven "apache-maven-3.8.6" 
    }

    stages {
        stage('Git Clone') {
            steps {
            git credentialsId: 'github', url: 'https://github.com/kartikeyapro/ks.git'   
            }
            }
		stage('MVN Version') {
            steps {
             sh 'mvn --version'   
            }
            }
		stage('MVN Clean') {
            steps {
            sh 'mvn clean'    
            }
            }
			
		stage('MVN Validate') {
            steps {
            sh 'mvn validate'    
            }
            }
		stage('MVN Compile') {
            steps {
            sh 'mvn compile'    
            }
            }
			
		stage('MVN Test') {
            steps {
            sh 'mvn test'    
            }
            }
		stage('MVN Package') {
            steps {
            sh 'mvn package'    
            }
            }		
		 stage('MVN Deploy') {
            steps {
            sh 'mvn deploy'    
            }
            }		
        }
}
