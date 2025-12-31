pipeline {
    agent any

    tools {
        jdk 'jdk-17-corretto'
        maven 'Maven3'
    }

    stages {

        stage('Checkout from GitHub') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/USERNAME/REPOSITORY.git'
            }
        }

        stage('Build Maven Application') {
            steps {
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            echo '✅ Build successful using JDK 17 Amazon Corretto'
        }
        failure {
            echo '❌ Build failed'
        }
    }
}
