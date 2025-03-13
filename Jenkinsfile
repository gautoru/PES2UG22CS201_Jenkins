pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/<user>/<repo>.git'
            }
        }

        stage('Build') {
            steps {
                sh 'g++ main.cpp -o YOUR_SRN-1'
            }
        }

        stage('Test') {
            steps {
                sh './PES2UG22CS201'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                git config --global user.email "your-email@example.com"
                git config --global user.name "your-username"
                git add main.cpp
                git commit -m "Added new working .cpp file"
                git push origin main
                '''
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
    }
}
