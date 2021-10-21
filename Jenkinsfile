pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                docker build --tag flask-app .
            }
        }
        stage('Login') {
            steps {
                echo 'logging..'
                docker login -u="benjaminfrancis10" -p="9747065338@ben" 
            }
        }
        stage('Push') {
            steps {
                echo 'Deploying....'
                docker push benjaminfrancis10/flask-docker
            }
        }
        stage('Run') {
            steps {
                echo 'Deploying....'
                
            }
        }
    }
}
