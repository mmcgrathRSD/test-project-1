pipeline {
	environment {
		DOCKER_HOST = "hub.docker.com/"
		DOCKER_IMAGE = "mokeseven7/php-cli:latest"
	}

	agent any

	stages {
	
	stage('Checkout') {
			steps {
				checkout scm
			}
		}

		stage('Test Docker is installed...') {
			steps {
				sh 'sudo docker info'
			}
		}

		stage('Pull Docker Container') {
			steps {
				sh 'export PWD=`pwd`'
				sh 'ls -la'
			}
		}

		stage('Deploy') {
			steps {
				echo 'Deploying....'
			}
		}
		
	}

}

