pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build 'PES2UG22CS240-1'
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
                echo 'Starting deployment...'
                sh 'exit 1' // 🔥 Intentional error to make deployment fail
            }
        }
    }

    post {
        failure {
            error "Pipeline failed"
        }
    }
}
