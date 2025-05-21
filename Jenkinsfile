pipeline {
    agent any

    environment {
        // You can define virtualenv path or environment variables here
    }

    stages {
        stage('Clone') {
            steps {
                echo "Cloning GitHub repository..."
            }
        }

        stage('Install Requirements') {
            steps {
                sh '''
                python --version
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest tests/'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                mkdir -p /tmp/python-app-deploy
                cp -r * /tmp/python-app-deploy
                echo "Deployed to /tmp/python-app-deploy"
                '''
            }
        }
    }
}
