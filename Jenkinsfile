node {
    stage('Preparation') {
        catchError(buildResult: 'SUCCESS') {
            sh 'docker stop pipelinetester'
            sh 'docker rm pipelinetester'
        }
    }
    stage('Build') {
        build 'pipelinetester'
    }
    stage('Results') {
        build 'pipelinetester'
    }
}
