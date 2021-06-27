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
        sh 'chmod +x gradlew && ./gradlew clean spotlessApply && ./gradlew init &&./gradlew build'
      }
    }

    stage('Test') {
      steps {
        echo 'Test'
      }
    }

    stage('Validate') {
      steps {
        echo 'Validate'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy'
      }
    }

  }
}