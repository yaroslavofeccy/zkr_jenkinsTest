pipeline {
    agent any

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

                go test ./
            }
        }

        stage('Build') {
            steps{
                echo "Build step"

                go build ./
            }
        }
    }
}