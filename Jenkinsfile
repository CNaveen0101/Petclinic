pipeline{
    agent any

    tools {
      maven 'Maven'
    }

    environment{
        Sonar = "Sonar-Scanner"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "code checkout passed successfully"
            }
        }

        stage ('Build Stage') {
            steps {
                sh 'mvn clean package'
            }

        }

        stage ('Test') {
            steps {
                sh 'mvn sonar:sonar'
                
            }
        }
    }
}
