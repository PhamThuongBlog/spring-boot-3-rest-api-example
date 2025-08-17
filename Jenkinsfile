pipeline {
  agent any
  tools {
    maven 'M3'  // nếu đã config Maven tool; nếu dùng mvnw thì bỏ tools { } đi
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
        // Nếu dùng mvn có trên PATH
        // sh 'mvn clean install'
        // Hoặc dùng Maven Wrapper:
        sh './mvnw clean install'
      }
    }
  }
}
