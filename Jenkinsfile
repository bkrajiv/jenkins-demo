pipeline {
    agent any
tools {
        maven 'maven3'
    }

    
    stages {

        stage('Checkout') {
            steps {
                echo 'Source code checked out from GitHub!!!'
            }
        }

        stage('Build') {
            steps {
      //  sh './mvnw clean package'    permission denied
                 sh 'chmod +x mvnw'
                 sh './mvnw clean package'
                 sh 'mvn clean package' 
            }
        }


        stage('Check Tools') {
                steps {
                        sh '''
                            echo "Java version:"
                            java -version
                
                            echo "Maven version:"
                            mvn -version
                
                            echo "Maven location:"
                            which mvn
                        '''
                    }
                }

             stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Archive JAR') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar',
                                 fingerprint: true
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
}
}
