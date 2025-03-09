pipeline {
    agent any

    stages{
        stage('Checkout') {
            echo "Checkout step"

            checkout scm
        }

        stage('Test') {
            echo "Test stage"

            go test ./
        }

        stage('Build') {
            echo "Build step"

            go build ./
        }
    }
}