pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code checked out from GitHub!!!'
            }
        }

        stage('Build') {
            steps {
                bat '.\\mvnw.cmd clean package'
            }
        }

    }
}
