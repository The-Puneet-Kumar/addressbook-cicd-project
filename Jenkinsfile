pipeline {
    agent any

    tools {
        jdk 'jdk-17-corretto'
        maven 'Maven3'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/The-Puneet-Kumar/addressbook-cicd-project.git'
            }
        }

        stage('Verify Java Version') {
            steps {
                sh 'java --version'
            }
        }

        stage('Build Maven App') {
            steps {
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            echo '✅ Build Successful with JDK 17'
        }
        failure {
            echo '❌ Build Failed'
        }
    }
}
