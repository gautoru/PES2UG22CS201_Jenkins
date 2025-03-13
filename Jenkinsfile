pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o output program.cpp'  // Compile the C++ file
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './output'  // Run the compiled C++ program
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
