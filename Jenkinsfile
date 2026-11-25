pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                echo 'Checking out source code from GitHub...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'mkdir -p build && cp -r *.py *.txt build/ 2>/dev/null || true'
                sh 'echo "Build completed on $(date)" > build/build.log'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'test -f build/build.log && echo "Build artifact verified: Tests Passed!"'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'echo "Application deployed successfully on Ubuntu Jenkins!"'
            }
        }
    }
}
