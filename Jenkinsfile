pipeline {
    agent any

    tools {
        maven 'Maven Build'
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
    }
}
