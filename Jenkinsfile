pipeline {
    agent {
        docker {
            label 'docker'
            image 'golang:1.11.2-alpine3.8'
        }
    }
    stages {
        stage('build') {
            steps {
                sh 'go build'
            }
        }
    }
}
