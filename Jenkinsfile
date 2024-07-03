pipeline {
    agent any
    environment {
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk1.8.0_361'
        PYTHON_HOME = 'C:\\Users\\cdied\\AppData\\Local\\Microsoft\\WindowsApps'
        PATH = "${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}"
    }
    stages {
        stage('Checkout') {
            steps {
               git branch: 'main', url: 'https://github.com/awoune/Tpjenkin.git'
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
                        bat 'java HelloWorld'
                        bat 'python hello.py'
                        // Add your Windows-specific build commands here
                    }
                }
            }
        }
    }
}
