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
        sh 'chmod +x gradlew && ./gradlew clean spotlessApply && ./gradlew init && ./gradlew build  && ./gradlew sonarqube -Dsonar.projectKey=grupo:undefined -Dsonar.host.url=http://localhost:9000 -Dsonar.login=5a3973d4209ed74647fcd13c032315edfbe2a54d --warning-mode all'
      }
    }

    stage('Analyze') {
      tools {
        jdk 'JDK11'
      }
      steps {
        echo 'Analyze'
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