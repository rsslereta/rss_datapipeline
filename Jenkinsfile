pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage('build') {
            steps {
                echo 'Building..'
                sh 'python --version'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'python --version'
            }
        }
        stage('Develop') {
            steps {
                echo 'Deploying....'
                sh 'python --version'
            }
        }
        stage('Production') {
            steps {
                echo 'Deploying....'
                sh 'python --version'
            }
        }
    }
}
