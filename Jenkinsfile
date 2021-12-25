pipeline {
	agent {  label 'ec2-linux-node' }
	stages {
		stage('---clean---'){
			tools {
				maven 'maven-3.8.3'
			}
			steps {
				
				sh "mvn clean"
			}
		}
		stage('---test---') {
			tools {
				maven 'maven-3.8.2'
			}
			steps {
				
				sh "mvn test"
			}
		}
		stage('---package---'){
			
			steps {
				
				sh "mvn package"
			}
		}
		stage('install') {
			tools {
				maven 'maven-3.8.3'
			}
			steps {
				sh "mvn install"
			}
	}
	post {
		success {
			echo 'realtime job was built successfully'
		}
		failure {
			echo 'job was not build..it was failed'
		}
	}
}
}
