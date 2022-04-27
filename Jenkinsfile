
pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}

	stages {

		stage('Build') {

			steps {
				sh 'docker build -t gururajp005/nodeapp:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo 1e1f7b6d-a96e-42f3-8d1a-dcbfe1575777 | docker login -u gururajp005 --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push gururajp005/nodeapp:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}

