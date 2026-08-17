pipeline {
    agent any

    stages {
        stage('Hello'){
            steps {
                echo "Hello, Jenkeins"
                echo "this is my first pipeline"
            }
        }
        stage('System Information'){
            steps {
                sh 'whoami'
                sh 'hostname'
                sh  'pwd'
            }
        }
        stage('Build'){
            steps{
                echo "building application..."
            }
        }
        stage('test'){
            steps{
                echo "running tests..."
            }
        }
    }
}