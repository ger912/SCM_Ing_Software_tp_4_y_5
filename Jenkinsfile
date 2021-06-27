pipeline {
  agent any
  stages {
    stage('Build') {
      tools {
        jdk 'JDK11'
      }
      steps {
        sh 'java --version'
        git(url: 'https://github.com/ger912/SCM-TP4-IngSoftware.git', branch: 'master', credentialsId: 'ger912')
        sh 'chmod +x gradlew && ./gradlew init && ./gradlew clean spotlessApply && ./gradlew build'
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
