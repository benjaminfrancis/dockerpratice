pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh ' docker build --tag benjaminfrancis10/flask-docker .'
            }
        }
        stage('Login') {
            steps {
                echo 'logging..'
                sh ' docker login -u="benjaminfrancis10" -p="9747065338@ben" '
            }
        }
        stage('Push') {
            steps {
                echo 'Deploying'
                sh 'docker push benjaminfrancis10/flask-docker'
            }
        }
        stage('Run') {
            steps {
                echo 'Deploying..'
            }
        }
    }
}
