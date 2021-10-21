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
                bat '''FOR /F %%i IN ('curl -o /dev/null -s -w "%%{http_code}" www.google.com') DO set VARIABLE=%%i'''
                bat '''if %VARIABLE%==200 ('docker ps') else ('docker images')'''
            }
        }
        stage('Run') {
            steps {
                echo 'Deploying..'
            }
        }
    }
}
