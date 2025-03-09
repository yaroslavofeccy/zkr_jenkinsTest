pipeline {
    agent { docker { image 'golang:1.24.0-alpine3.21' } }

    stages{
        stage('Checkout') {
            steps{
                echo "Checkout"

                checkout scm
            }
        }

        stage('Test') {
            steps{
                echo "Test stage"

                sh 'go test ./'
            }
        }

        stage('Build') {
            steps{
                echo "Build step"

                sh 'go build ./'
            }
        }

        stage('Run') {
            steps{
                echo "Run step"

                sh 'go run ./'
            }
        }
    }
}