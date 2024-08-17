pipeline {
    agent any

    tools {
        maven 'Maven'  // This is correct for Maven
    }

    stages {
        stage('Checkout') {
            steps {
                echo "code checkout passed successfully"
            }
        }

        stage('Test') {
            steps {
                withSonarQubeEnv('Sonar') {
                    sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Build Stage') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Dependency Check') {
            steps {
                dependencyCheck additionalArguments: '--format XML --format HTML --failOnCVSS 7', 
                    odcInstallation: 'Default', 
                    scanPath: '/var/lib/jenkins/workspace/A/target/*.jar'  // Corrected wildcard usage
            }
        }
    }
}
