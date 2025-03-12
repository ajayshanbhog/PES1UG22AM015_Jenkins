pipeline {
    agent any
    stages {        
        stage('Build') {
            steps {
                build 'PES1UG22AM015-1'
                sh 'g++ main/hello.cpp -o output'
            }
        }
        
        stage('Test') {
            steps {
                // Error in this stage
                sh './output_invalid'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}