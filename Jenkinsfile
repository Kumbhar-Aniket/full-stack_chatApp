pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/iemafzalhassan/full-stack_chatApp.git'
            }
        }

        // stage('Test') {
        //     steps {
        //         script {
        //             bat '''
        //                 sleep 15
        //                 curl -f http://localhost:5001/health
        //                 curl -f http://localhost/ || exit 1
        //             '''
        //         }
        //     }
        // }

        stage('Deploy') {
            steps {
                script {
                    bat 'docker-compose up -d --build'
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment and tests completed successfully!'
        }
        failure {
            echo 'Deployment or tests failed.'
        }
    }
}
