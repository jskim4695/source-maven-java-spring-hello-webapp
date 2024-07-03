pipeline {
  agent any

  triggers {
    pollSCM('* * * * *')
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', 
        url: 'URL'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('Deploy') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'CREDENTIAL_ID', url: 'DEPLOY_URL')], contextPath: null, war: 'APPLICATION_WAR_BUILD_PATH'
      }
    }
  }
}
