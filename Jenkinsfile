pipeline {
    agent { 
        node {
            label 'docker-agent-python'
        }
    }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building..."
                sh '''
                    cd myapp
                    
                    # Create a virtual environment named 'venv'
                    python3 -m venv venv
                    
                    # Activate it and install the python 'fire' package
                    . venv/bin/activate
                    
                    pip install fire
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing..."
                sh '''
                    cd myapp
                    
                    # Activate the same virtual environment before testing
                    . venv/bin/activate
                    
                    python3 hello.py
                    python3 hello.py --name=Brad
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver...'
                sh '''
                    echo "doing delivery stuff..."
                '''
            }
        }
    }
}
