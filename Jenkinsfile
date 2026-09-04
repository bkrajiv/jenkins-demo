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
      //  sh './mvnw clean package'    
                 sh 'chmod +x mvnw'
                 sh './mvnw clean package'
            }
        }

    }
}
