pipeline {
    agent any

    environment {
        JAVA_HOME = "C:\\Program Files\\Java\\jdk-21"
        PATH = "${JAVA_HOME}\\bin;${env.PATH}"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/anushriadapawar/DevOps-CA2-task.git'
            }
        }

        stage('Compile Java') {
            steps {
                bat '''
                javac -version
                javac -cp "selenium/lib/*;selenium/lib/libs/*" selenium/src/FormTest.java
                '''
            }
        }

        stage('Run Selenium Test') {
            steps {
                bat '''
                java -version
                java -cp "selenium/src;selenium/lib/*;selenium/lib/libs/*" FormTest
                '''
            }
        }

    }

    post {
        success {
            echo 'Build SUCCESS'
        }

        failure {
            echo 'Build FAILED'
        }
    }
}