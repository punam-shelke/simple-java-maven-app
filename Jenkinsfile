pipeline {
    agent any
    tools {
        maven 'maven-3.8.6'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building the application"
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}