
pipeline {
    agent any
    environment {
        JAVA_HOME = '/usr/bin/java'
        PYTHON_HOME = '/usr/bin'
        PATH = "${env.PATH}:${JAVA_HOME}:${PYTHON_HOME}"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/hrhouma/hello-python.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'echo "Running on Unix"'
                        sh 'javac HelloWorld.java'
                        sh 'java HelloWorld'
                        sh 'python3 hello.py'
                    } else {
                        withEnv(["JAVA_HOME=C:\\Program Files\\Java\\jdk1.8.0_202",
                                 "PYTHON_HOME=C:\\Users\\rehou\\AppData\\Local\\Microsoft\\WindowsApps",
                                 "PATH=%JAVA_HOME%\\bin;%PYTHON_HOME%;%PATH%"]) {
                            bat 'echo "Running on Windows"'
                            bat 'javac HelloWorld.java'
                            bat 'java HelloWorld'
                            bat 'python hello.py'
                        }
                    }
                }
            }
        }
    }
}
