#!/usr/bin.env groovy

pipeline {   
    agent any
    stages {
        stage("test") {
            steps {
                script {
                    echo "Testing the application..."

                }
            }
        }
        stage("build") {
            steps {
                script {
                    echo "Building the application..."
                    def dockercmd = 'docker run -d -p3000:3000 vuyalaarun/node-app:1.4.0'
                    sshagent(['aws-server-key']) {
                   sh "ssh ec2-user-o StrictHostKeyChecking=no 2-user@3.135.211.122 ${dockercmd}"
                 }
                }
            }
        }

        stage("deploy") {
            steps {
                script {
                    echo "Deploying the application..."
                }
            }
        }               
    }
} 
