@Library('shared') _

pipeline {
    agent { label  'ubuntu-agent' }

    stages {
        stage("Hello Groovy") {
            steps {
                script {
                    hello() // Assumes this function exists in your shared library under vars/hello.groovy
                }
            }
        }

        stage("Hello First") {
            steps {
                echo "hello from CI/CD pipeline"
            }
        }

        stage("Create Folder") {
            steps {
                sh "mkdir -p hello-from-pipeline"
            }
        }

        stage("Bye from Pipeline") {
            steps {
                echo "Bye dosto"
            }
        }
    }
}
