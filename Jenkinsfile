pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                // Sử dụng bước tích hợp của Jenkins để checkout code
                git url: 'https://github.com/ThangLD203/todolist.git', branch: 'main'
            }
        }
        stage('Build Code') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                // Chạy ứng dụng sau khi build
                sh 'npm run serve'
            }
        }
    }

    post {
        always {
            // Clean workspace sau khi hoàn thành pipeline
            cleanWs()
        }
        failure {
            echo 'Pipeline failed!'
        }
        success {
            echo 'Pipeline succeeded!'
        }
    }
}
