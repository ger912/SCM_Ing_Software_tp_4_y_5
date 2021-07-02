pipeline {
  agent any
  stages {
    stage('Build') {
      tools {
        jdk 'JDK11'
      }
      steps {
        sh 'java --version'
        git(url: 'https://github.com/ger912/SCM_Ing_Software_tp_4_y_5/', branch: 'master', credentialsId: 'ger912')
        sh '''chmod +x gradlew && ./gradlew clean spotlessApply && ./gradlew sonarqube -Dsonar.host.url=http://localhost:9000 &&./gradlew init && ./gradlew build'''
      }
    }

    stage('Validate') {
      steps {
        withSonarQubeEnv() { // Will pick the global server connection you have configured
        sh './gradlew sonarqube'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy'
      }
    }

  }
}
