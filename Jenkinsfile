pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/muntaser4github/-teavm-maven-webapp.git', branch: 'master', credentialsId: 'github-user')
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
