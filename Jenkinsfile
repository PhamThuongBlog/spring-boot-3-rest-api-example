pipeline {
  agent any
  tools {
    maven 'M3'
  }
  stages {
    stage('Hello') {
      steps {
        echo "Hello You"
      }
    }
    stage('Checkout') {
      steps {
        git url: 'https://github.com/bezkoder/spring-boot-3-rest-api-example.git', branch: 'master'
      }
    }
    stage('Build & Test') {
      steps {
        sh 'chmod +x mvnw'
        sh './mvnw clean install'
      }
    }
  }
}
