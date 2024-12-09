pipeline {
    agent any
    options {
        checkoutToSubdirectory('src')
    }
    stages {
      stage('checkout') {
        steps {
          git branch: 'version1', url: 'https://github.com/akhila6522/spring-boot-microservices.git'
        }
      }
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
    }
}
  
