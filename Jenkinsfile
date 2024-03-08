pipeline {
    agent any 
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/PES2UG21CS068_Jenkins/Jenkins-git']]])
            }
        }
        stage('Build') {
            steps {
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy'
            }
            post {
                failure {
                    error 'Pipeline failed'
                }
            }
        }
    }
}
