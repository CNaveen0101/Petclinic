pipeline{
    agent any

    tools {
        'Maven'
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
