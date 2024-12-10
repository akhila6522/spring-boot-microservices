pipeline {
    agent any
    options {
        checkoutToSubdirectory('src')
    }
    stages {
      stage('checkout') {
        steps {
          git branch: 'master', url: 'https://github.com/akhila6522/spring-boot-microservices.git'
        }
      }
        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
         stage('Archive JARs') {
            steps {
                // Archive built JAR files
                script {
                    def services = ['product-service', 'order-service', 'inventory-service', 
                                    'discovery-server', 'api-gateway', 'notification-service']
                    services.each { service ->
                        archiveArtifacts artifacts: "${service}/target/*.jar", allowEmptyArchive: false
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Build and packaging completed successfully!'
        }
        failure {
            echo 'Build failed. Please check the logs.'
        }
    }
}
  
