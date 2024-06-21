pipeline {
    agent any
    environment {
        PATH = "${env.PATH}:/usr/bin/python3"
    }
    stages {
        stage('Checkout') {
            steps {
                git clone 'https://github.com/hrhouma/hello-python'
            }
        }
        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'echo "Running on Unix"'
                        // Add your Unix-specific build commands here
                    } else {
                        bat 'echo "Running on Windows"'
                        // Add your Windows-specific build commands here
                    }
                }
            }
        }
    }
}
