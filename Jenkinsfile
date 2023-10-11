pipeline {
	agent { label 'Jenkins-Agent'}
	tools {
		maven 'Maven3'
		jdk 'Java17'
	}
	stages{
		stage('Cleanup Workspace'){
			steps{
				cleanWs()
			}
		}

		stage('Check Out from SCM'){
			steps{
				git branch: 'dev', credentialsId : 'github', url: 'https://github.com/Rudra2912/register-app.git'
			}
		}
		stage('Build application'){
			steps{
				sh "mvn clean package"
			}
		}

		stage('Test Application'){
			steps{
				sh "mvn test"
			}
		}
	}
}
