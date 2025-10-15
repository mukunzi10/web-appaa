pipeline {
    agent any

    tools {
        nodejs 'NodeJS_18'   // Configured in Jenkins Global Tools
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
        junit 'coverage/junit.xml'
    }
}
}
