pipeline {
    agent any

    tools {
        // Make sure "NodeJS_18" is defined in:
        // Manage Jenkins → Global Tool Configuration → NodeJS
        nodejs 'NodeJS_18'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/your-org/product-inventory.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'npm test'
            }
        }
    }

    post {
        always {
            // Publish Jest JUnit report (ensure jest-junit is configured)
            junit 'coverage/junit.xml'
        }
    }
}
