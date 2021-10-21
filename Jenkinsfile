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
                bat '''FOR /F %i IN ('curl -o /dev/null -s -w "%{http_code}" www.google.com') DO set VARIABLE=%i'''
                bat 'echo %VARIABLE%'
                bat '''if %VARIABLE%==200 (echo "flask running") else (echo "Unknown value")'''
                echo 'success'
            }
        }
        stage('Run') {
            steps {
                echo 'Deploying.'
                bat 'docker run -d -p 5003:5001  --name flask_project3 benjaminfrancis10/flask-docker'  
            }
        }
    }
}
