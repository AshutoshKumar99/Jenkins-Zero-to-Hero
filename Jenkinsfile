pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
                docker { 
                    image 'maven:3.8.1-adoptopenjdk-11' 
                }
            }
            steps {
                dir('java-hello-world-with-maven') {
                    sh 'mvn clean install'
                }
            }
        }
        stage('Front-end') {
            agent {
                docker { 
                    image 'node:16-alpine' 
                }
            }
            steps {
                dir('node-express-hello-world') {  
                    sh 'node --version'
                }
            }
        }
    }
}
