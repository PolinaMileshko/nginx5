pipeline {
    agent any 
    stages {
        stage('Login') { 
            steps {
                sh 'docker login -u $USERNAME -p $PASSWORD'
            }
        }
        stage('Docker build container nginx') { 
            steps {
                sh """
                  docker build -t polymiles/lab3:1.{env.BUILD_NUMBER} .
                  docker push polymiles/lab3:1.{env.BUILD_NUMBER}
                """
            }
    }
}
