pipeline{
    agent any

    tools {
      maven 'Maven'
      owasp 'OWASP'
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
                withSonarQubeEnv('Sonar') {
                sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Dependency Check') {
          steps {
            dependencyCheck additionalArguments: '--format XML --format HTML --failOnCVSS 7', 
                odcInstallation: 'Default', 
                scanPath: '**/*.jar'
         }
        }

    }
}

