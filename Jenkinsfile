pipeline {
  agent any

  environment {
    SONAR_SCANNER = 'Sonar-Scanner'
  }

  stages {
    stage('Code-Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/CNaveen0101/Petclinic'
      }
    }

    stage('Sonar-qube-analysis') {
      steps {
        withSonarQubeEnv('Sonar-Scanner') {
          sh 'mvn sonar:sonar'
        }
      }
    }
  }
}
