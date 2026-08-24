pipeline{
    agent{
        label 'myslave'
    }
    stages{
        stage('Download'){
            steps{
                git 'https://github.com/IntelliqDevops/maven.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn package'
            }
        }
            
        }
    }

