//Todos: 
//1. Fix perms on server so docker commands dont need to run with sudo

pipeline {
	environment {
		DOCKER_HOST = "hub.docker.com/"
		DOCKER_IMAGE = "mokeseven7/php-cli:latest"
		DOCKER_IMAGE_NAME = 'my-php-app'
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

	stage('Remove Old Image') {
		steps {
			echo 'Removing old container.'
			sh '''
			if [ ! "$(sudo docker ps -q -f name=$DOCKER_IMAGE_NAME)" ]; then
				if [ "$(sudo docker ps -aq -f status=exited -f name=$DOCKER_IMAGE_NAME)" ]; then
					# cleanup
					sudo stop $DOCKER_IMAGE_NAME
					sudo docker rm $DOCKER_IMAGE_NAME
				fi
			fi
			'''
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
			sh 'sudo docker build -t $DOCKER_IMAGE_NAME . '
		}
	}

	stage('Execute Containerr') {
		steps {
			echo 'Executing PHP Script'
			sh 'sudo docker run -i --rm --name my-running-app $DOCKER_IMAGE_NAME'
		}
	}
		
	}
}

