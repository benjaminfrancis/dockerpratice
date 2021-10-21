pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                bat 'docker build --tag flask-app .'
            }
        }
        stage('Login') {
            steps {
                echo 'logging..'
                bat 'docker login -u="benjaminfrancis10" -p="9747065338@ben" '
            }
        }
        stage('Push') {
            steps {
                echo 'Deploying' 
                sh '''IF 200==200 ('docker ps') ELSE ('docker images')'''
               
            }
        }
        stage('Run') {
            steps {
                echo 'Deploying..'
            }
        }
    }
}
