@Library('shared') _

pipeline {
     agent { label 'ubuntu-agent' }
    // agent any

    stages {
        stage('Shared Function') {
            steps {
                script {
                    echo'ubuntu agent is down i am checking weather is will or not'
                    echo 'Calling shared library function'
                    hello() // This will call the function defined in vars/hello.groovy
                }
            }
        }

        stage('Code') {
            steps {
                echo 'Cloning the app repository'
                git url: 'https://github.com/widohulk-avg/django-notes-app.git', branch: 'main'

                echo 'Building Docker image'
                sh 'docker build -t notes-app:latest .'
                echo 'Docker build completed'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add test commands here
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build steps here
            }
        }

        stage('Deployment') {
            steps {
                echo 'Deploying the app...'
                sh 'docker compose down'
                sh 'docker compose up -d'
            }
        }
    }
}
