pipeline{

	agent {label 'linux'}

	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}

	stages {
	    
	    stage('gitclone') {

			steps {
				git 'https://github.com/benjaminfrancis/dockerpratice.git'
			}
		}

		stage('Build') {

			steps {
				sh 'docker build -t benjaminfrancis10/docker-assingments:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push benjaminfrancis10/docker-assingments:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}
