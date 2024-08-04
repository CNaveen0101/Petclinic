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

        stage('Deploy') {
            steps {
                sh 'sudo cp /var/lib/jenkins/workspace/test/target/petclinic.war /home/ubuntu/apache-tomcat-9.0.91/webapps'
            }
        }
    }
}
