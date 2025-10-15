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
pipeline {
agent any
tools {
nodejs 'NodeJS_18' // NodeJS tool defined in Jenkins > Global Tools
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
junit 'test-results/junit.xml'
}
}
}