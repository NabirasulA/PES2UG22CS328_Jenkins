pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'g++ -o hello_exec main/nonexistent_file.cpp'  // Intentional error: nonexistent_file.cpp doesn't exist
            }
        }
        stage('Test') {
            steps {
                sh './hello_exec'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline Failed!'
        }
    }
}
