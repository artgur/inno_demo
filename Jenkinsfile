#!groovy
pipeline {
    agent {
        docker {
            label 'docker'
            image 'golang:1.11.2-alpine3.8'
        }
    }
    stages {
        stage('test') {
            steps {
                sh 'go get -u github.com/jstemmer/go-junit-report'
                sh 'go test -v 2>&1 | go-junit-report > report.xml'

            }
            post {
                always {
                    junit 'report.xml'
                }
            }
        }
        stage('build') {
            steps {
                sh 'go build'
            }
            post {
                success {
                    archiveArtifacts 'inno_demo'
                }
            }
        }
    }
}
