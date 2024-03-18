pipeline {
    agent any 
    stages {
        stage('Login') { 
            steps {
                script {
                    sh "docker login -u $USERNAME -p $PASSWORD"
                }
            }
        }
        stage('Docker build container go-application') { 
            steps {
                script {
                    sh """
                      docker build -t polymiles/lab3:1.${env.BUILD_NUMBER} .
                      docker push polymiles/lab3:1.${env.BUILD_NUMBER}
                    """
                }
            }
        }
    }
}
