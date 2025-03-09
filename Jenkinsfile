pipeline {
    agent {
        kubernetes {
            yaml '''
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: golang
    image: golang:1.24.0-alpine3.21
    command:
    - cat
    tty: true
'''
        }
    }

    stages {
        stage('Checkout') {
            steps {
                container('golang') {
                    echo "Checkout"
                    checkout scm
                }
            }
        }

        // stage('Test') {
        //     steps {
        //         container('golang') {
        //             echo "Test stage"
        //             sh 'go test ./...'
        //         }
        //     }
        // }

        stage('Build') {
            steps {
                container('golang') {
                    echo "Build step"
                    sh 'go build ./...'
                }
            }
        }

        stage('Run') {
            steps {
                container('golang') {
                    echo "Run step"
                    sh 'go run ./main.go'  
                }
            }
        }
    }
}