pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/mukunzi10/web-appaa'
            }
        }

        stage('Verify Tools') {
            steps {
                sh 'php -v'
                sh 'npm -v'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
    }

    post {
        always {
            junit 'coverage/junit.xml'
        }
    }
}
