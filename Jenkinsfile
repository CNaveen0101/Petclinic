pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    environment {
        SONARQUBE_SCANNER="Sonar"
    }

    stages{

        stage('Checkout') {
            steps {
                echo "Code Checkout Passed"
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
