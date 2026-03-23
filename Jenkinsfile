pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/anushriadapawar/DevOps-CA2-task.git'
            }
        }

        stage('Compile Java') {
            steps {
                bat '''
                javac -cp "selenium/lib/*;selenium/lib/libs/*" selenium/src/FormTest.java
                '''
            }
        }

        stage('Run Selenium Test') {
            steps {
                bat '''
                java -cp "selenium/src;selenium/lib/*;selenium/lib/libs/*" FormTest
                '''
            }
        }

    }

    post {
        success {
            echo 'Build SUCCESS - Form tested successfully'
        }

        failure {
            echo 'Build FAILED'
        }
    }
}