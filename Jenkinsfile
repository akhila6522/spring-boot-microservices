pipeline {
    agent any
    stages {
      stage('checkout') {
        steps {
          git branch: 'master', url: 'https://github.com/akhila6522/spring-boot-microservices.git'
        }
      }
        stages('Build') {
            steps {
                sh.'mvn clean package'
            }
        }
        stages('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
  
