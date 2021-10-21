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
                bat 'docker push benjaminfrancis10/flask-docker'
            }
        }
        stage('Run') {
            steps {
                echo 'Deploying.'
                bat 'docker run -d -p 5002:5001  --name flask_project2 benjaminfrancis10/flask-docker'
                
            }
        }
    }
}
