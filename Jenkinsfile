pipeline {
  agent any

  stages {
    // Stage 1: Code Checkout
    stage('Code-Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/CNaveen0101/Petclinic'
      }
    }

    // Stage 2: SonarQube Analysis
    stage('SonarQube Analysis') {
      steps {
        withSonarQubeEnv('Sonar-Scanner') { // Replace 'SonarQube-Server' with your SonarQube configuration name
          sh """
          mvn sonar:sonar \
            -Dsonar.projectKey=Petclinic \
            -Dsonar.host.url=http://192.168.1.9:9000 \
            -Dsonar.login=Sonar-Cred
          """
        }
      }
    }
  }
}
