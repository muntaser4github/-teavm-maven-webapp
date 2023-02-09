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
 stage('Deploy') {
      steps {
        sshagent(['tomcat_server']) {
sh  'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/-teavm-maven-webapp/target/teavm-maven-webapp-1.0-RELEASE.war ubuntu@172.31.0.57:/opt/apache-tomcat-8.5.85/webapps'
}
      }
    }
  }
}
