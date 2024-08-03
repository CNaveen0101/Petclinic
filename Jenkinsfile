pipeline {
    agent any

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
    }
}
