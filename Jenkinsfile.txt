pipeline {
    agent { 
        node {
            label 'docker-agent-alpine'
            }
      }
    stages {
        stage('Build') {
            steps {
                echo "Building..."
                sh '''
                echo "I am doing build stuff..."
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing..."
                sh '''
                echo "I am doing test stuff..."
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo "Deliver..."
                sh '''
                echo "I am doing delivery stuff..."
                '''
            }
        }
    }
}
