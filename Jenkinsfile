pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Intentional error: The file "nonexistent_file.cpp" does not exist
                sh 'g++ -o hello_exec main/nonexistent_file.cpp'
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
