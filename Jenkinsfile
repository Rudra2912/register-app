pipeline {
	agent { label 'Jenkins-Agent'}
	tools {
		maven 'Maven3'
		jdk 'Java17'
	}
	stages{
		stage('Cleanup Workspace'){
			step{
				cleanWs()
			}
		}

		stage('Check Out from SCM'){
			step{
				git branch: 'Dev', credentialsId : 'github', url: 'https://github.com/Rudra2912/register-app.git'
			}
	}

		stage('Build application'){
			step{
				sh "mvn clean package"
			}
		}

		stage('Test Application'){
			step{
				sh "mvn Test"
			}
		}
}
