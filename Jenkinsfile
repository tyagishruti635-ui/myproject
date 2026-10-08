pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/tyagishruti635-ui/myproject.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myproject:${BUILD_NUMBER} .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker run --rm myproject:${BUILD_NUMBER}'
            }
        }
    }
    post {
        success { echo 'Build successful' }
        failure { echo 'Build failed' }
    }
}
