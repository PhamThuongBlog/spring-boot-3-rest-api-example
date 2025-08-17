pipeline {
    agent any

    tools {
        maven "Maven3"   // Tên Maven đã cấu hình trong Jenkins (Global Tool)
        jdk "Java11"     // Tên JDK đã cấu hình trong Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/PhamThuongBlog/spring-boot-3-rest-api-example.git'
            }
        }

        stage('Build') {
            steps {
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Test') {
            steps {
                sh './mvnw test'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
