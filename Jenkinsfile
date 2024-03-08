pipeline {
    agent any

    stages {
          stage ('Build') {
      steps { 
        build 'PES2UG21CS068-1'
        sh 'g++ main.cpp -o output' 
      }
    }
        stage('Test') {
            steps {
                script {
                    // Print the output of the compiled .cpp file
                    sh './main'
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
