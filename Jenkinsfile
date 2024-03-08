pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build 'PES2UG21CS068-1'
                // Assuming main.cpp is in the root directory of your workspace
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                script {
                    // Print the output of the compiled .cpp file
                    sh './output' // Assuming the compiled executable is named 'output'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Add deployment steps here (e.g., copying artifacts to a server)
                    echo 'Deploy'
                }
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
