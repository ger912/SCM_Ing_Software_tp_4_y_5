pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''sh \'java --version\'
git(url: \'https://github.com/ger912/SCM-TP4-IngSoftware.git\', branch: \'master\', credentialsId: \'ger912\')
sh \'chmod +x gradlew && ./gradlew init && ./gradlew clean spotlessApply && ./gradlew build\'
'''
      }
    }

    stage('Test') {
      steps {
        echo 'test'
      }
    }

    stage('Validate') {
      steps {
        echo 'validate'
      }
    }

    stage('Deploy') {
      steps {
        echo 'deploy'
      }
    }

  }
}