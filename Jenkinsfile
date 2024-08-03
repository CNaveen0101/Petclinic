pipeline {
    agent any

    tools {
        maven 'Maven Build'
    }

    environment {
        SONARQUBESCANNER = "Sonar"
    }

    stages {

        stage('Checkout') {
            steps {
                echo "The code will be passed from github"
            }
        }

        stage('Compile') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
              withSonarQubeEnv('Sonar') {
                sh 'mvn sonar:sonar'
              }
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
