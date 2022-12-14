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
		stage('Maven Version') {
            steps {
             sh 'mvn --version'   
            }
            }
		stage('Code Clean') {
            steps {
            sh 'mvn clean'    
            }
            }
			
		stage('Code Validate') {
            steps {
            sh 'mvn validate'    
            }
            }
	    stage('SonarScan'){
			steps {
			sh 'mvn sonar:sonar -Dsonar.host.url=http://192.168.29.18:9000 -Dsonar.login=37ac2897d05c9505ef7da29166b56e5420e405ca'
			}
			}
		
		stage('Code Compile') {
            steps {
            sh 'mvn compile'    
            }
            }
			
		stage('Code Test') {
            steps {
            sh 'mvn test'    
            }
            }
		stage('Package') {
            steps {
            sh 'mvn package'    
            }
            }		
		 stage('Deploy') {
            steps {
            sh 'mvn deploy'    
            }
            }		
        }
}
