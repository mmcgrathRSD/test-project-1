pipeline {
	environment {
		DOCKER_HOST = "https://hub.docker.com/"
		DOCKER_IMAGE = "mokeseven7/php-cli:latest"
	}

	agent any

	stages {
	
	stage('Checkout') {
			steps {
				checkout scm
			}
		}

		stage('Build Docker') {
			steps {
				echo 'Test Docker is installed:.'
				sh 'docker info'
			}
		}

		stage('Test') {
			steps {
				echo 'Testing..'
			}
		}

		stage('Deploy') {
			steps {
				echo 'Deploying....'
			}
		}
		
	}

}

