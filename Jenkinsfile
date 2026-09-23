pipeline {
    agent any // Runs on whatever agent is available (or use your Windows agent label)

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing pytest...'
                bat 'pip install -r requirements.txt' 
            }
        }
        stage('Run Unit Tests') {
            steps {
                echo 'Running tests...'
                bat 'pytest test_app.py'
            }
        }
    }
    post {
        success {
            echo 'SUCCESS: All unit tests passed perfectly!'
        }
        failure {
            echo 'FAILURE: Unit tests failed. Check code!'
        }
    }
}
