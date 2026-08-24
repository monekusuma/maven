pipeline{
    agent any
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
        stage('Deploy'){
            steps{
                sh 'scp /home/ubuntu/myfolder/workspace/DeclarativePipelineOnSlave1/webapp/target/webapp.war ubuntu@172.31.34.104:/var/lib/tomcat10/webapps/testapp1'
            }
        }
            stage('tesing'){
                steps{
                    git 'https://github.com/IntelliqDevops/FunctionalTesting.git'
                    sh 'java -jar /home/ubuntu/myfolder/workspace/DeclarativePipelineOnSlave1/testing.jar'
                }
            }
            stage('Delivery'){
                steps{
                    sh 'scp /home/ubuntu/myfolder/workspace/DeclarativePipelineOnSlave1/webapp/target/webapp.war ubuntu@172.31.45.128:/var/lib/tomcat10/webapps/prodapp'
                }
            }
            
        }
    }

