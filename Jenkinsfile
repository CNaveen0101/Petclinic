pipeline{
    agent any

    tools {
        maven='Maven'
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
    }
}
