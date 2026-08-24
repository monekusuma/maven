@Library('mylibrary') _

pipeline {
    agent any

    stages {

        stage('Download') {
            steps {
                script {
                    cicd.gitDownload("maven")
                }
            }
        }

        stage('build') {
            steps {
                script {
                    cicd.buildArtifact()
                }
            }
        }

        stage('Deployment') {
            steps {
                script {
                    cicd.deployToTomcat("172.31.34.104", "testapp")
                }
            }
        }

        stage('testing') {
            steps {
                script {
                    git 'https://github.com/IntelliqDevops/FunctionalTesting.git'
                    cicd.runSelenium()
                }
            }
        }

        stage('Delivery') {
            steps {
                script {
                    cicd.deployToTomcat("172.31.45.128", "prodapp")
                }
            }
        }
    }
}
