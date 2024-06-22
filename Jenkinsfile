pipeline {
  agent any

  stages {
    stage('Git Checkout') {
      steps {
        echo " The First Stage Git Checkout Done"
      }
    }

    stage('Build Stage') {
      steps {
        sh 'mvn clean package'
      }
    }
  }
}
