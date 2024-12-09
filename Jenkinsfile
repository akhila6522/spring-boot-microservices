pipeline {
    agent any
    stages {
      stage('checkout') {
        steps {
          git branch: 'master', url: 'https://github.com/akhila6522/spring-boot-microservices.git'
        }
      }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
  
