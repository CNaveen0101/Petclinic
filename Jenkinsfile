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

        stage('Owasp Dependency') {
            steps {
                sh '/usr/local/bin/dependency-check/bin/dependency-check.sh --project "OWASP" --scan /var/lib/jenkins/workspace/test/target/'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo cp /var/lib/jenkins/workspace/test/target/petclinic.war /home/ubuntu/apache-tomcat-9.0.91/webapps'
            }
        }
    }
}
