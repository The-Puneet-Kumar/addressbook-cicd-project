pipeline {
    agent any

    tools {
        // Make sure this matches the name of the JDK in Jenkins Global Tool Configuration
        jdk 'java-17'
        maven 'Maven3'
    }

    stages {

        stage('Checkout from GitHub') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/The-Puneet-Kumar/addressbook-cicd-project.git'
            }
        }

        stage('Verify Java Version') {
            steps {
                sh 'java -version'
            }
        }

        stage('Maven Clean') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('Maven Build') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo '✅ Build Successful with JDK 17 Corretto'
        }
        failure {
            echo '❌ Build Failed'
        }
    }
}
