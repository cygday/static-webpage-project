pipeline {
  agent any
  

  environment {
    SONARQUBE_ENV = 'jenkins-sonar'
  }

  stages {
    stage('checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/cygday/static-webpage-project.git'
      }

    }

    stage('SonarQube Analysis') {
        steps {
          withSonarQubeEnv("${SONARQUBE_ENV}") {
            sh 'sonar-scanner'
          }
        }
    }
  }
}
