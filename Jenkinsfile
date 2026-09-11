pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code has been checked out'
                sh 'ls -la'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'

                sh '''
                    echo "Jenkins Build Number: $BUILD_NUMBER"
                    echo "Build Date: $(date)"

                    mkdir -p build

                    echo "Application built successfully" > build/app.txt
                    echo "Build Number: $BUILD_NUMBER" >> build/app.txt
                    echo "Built By: $(whoami)" >> build/app.txt
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'

                sh '''
                    test -f build/app.txt
                    echo "Test passed: build/app.txt exists"
                '''
            }
        }

        stage('Report') {
            steps {
                echo 'Build report:'

                sh '''
                    cat build/app.txt
                '''
            }
        }
    }
}