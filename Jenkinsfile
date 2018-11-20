pipeline {
    agent {
        docker {
            image 'golang:1.11.2-alpine3.8'
        }
    }
    stages {
        stage('build') {
            sh 'go build'
        }
    }
}
