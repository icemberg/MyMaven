pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage("Checkout") {
            steps {
                git branch: "main", url: "https://github.com/icemberg/MyMaven.git"
            }
        }
        stage("Build") {
            steps {
                sh 'mvn clean package'
            }
        }
        stage("Test") {
            steps {
                sh 'mvn test'
            }
        }
        stage("Run application") {
            steps {
                sh 'java -jar target/MyMaven-1.0-SNAPSHOT.jar'
            }
        }
    }
    
    post {
        success {
            echo "Build and deployment successful"
        }
        failure {
            echo "Build failed!"
        }
    }
}

