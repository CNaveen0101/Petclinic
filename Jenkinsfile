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
    
    stage('Scanning Stage') {
      steps {
        sh 'mvn sonar:sonar'
      }
    }
    stage('Deploy Stage') {
      steps {
        sh 'cp /var/lib/jenkins/workspace/Aws/target/petclinic.war  /opt/apache-tomcat-8.5.100/webapps'
      }
    }
  }
}
