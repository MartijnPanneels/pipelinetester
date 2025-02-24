pipeline {
    agent any

    stages {
        stage('Preparation') {
            steps {
                script {
                    catchError(buildResult: 'SUCCESS') {
                        sh 'docker stop pipelinetester || true'
                        sh 'docker rm pipelinetester || true'
                    }
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'docker build -t pipelinetester .'
                }
            }
        }

        stage('Run') {
            steps {
                script {
                    sh 'docker run -d --name pipelinetester pipelinetester'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
