pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ main.cpp -o PES1UG22AM015-1'
            }
        }

        stage('Test') {
            steps {
                sh './PES1UG22AM015-1'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
