pipeline {
    agent any

    tools {
        maven 'Maven'
        SONARQUBE_SCANNER 'Sonar'
    }

    stages{

        stage('Checkout') {
            steps {
                echo "Code Checkout Passed"
            }
        }

        stage('Test') {
            steps {
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
