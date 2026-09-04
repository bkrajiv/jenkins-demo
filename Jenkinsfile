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
}
}
