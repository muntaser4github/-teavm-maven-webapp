pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github_maven_account', url: 'https://github.com/muntaser4github/-teavm-maven-webapp.git']])
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
