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
				//TODO: Build Container
				sh 'export PWD=`pwd`'
				sh 'ls -la'
			}
		}

		stage('Build Docker Container') {
			steps {
				echo 'Building.'
				sh 'docker build -t my-php-app '
			}
		}

		stage('Execute Containerr') {
			steps {
				echo 'Executing PHP Script'
				sh 'docker run -it --rm --name my-running-app my-php-app'
			}
		}
		
	}

}

