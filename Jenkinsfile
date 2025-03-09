pipeline {
    agent any

    tools {
        go 'go1.24'
    }

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