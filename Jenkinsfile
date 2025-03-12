pipeline {
    agent any

    stages {
        stage('Pull from GitHub') {
            steps {
                sh 'git pull origin main'
            }
        }

        stage('Build') {
            steps {
                sh '''
                cd main
                make build
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'cd /var/jenkins_home/workspace/PES1UG22AM015-1/main/'
                sh './hello_exec'
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
