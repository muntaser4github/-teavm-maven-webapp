pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/muntaser4github/-teavm-maven-webapp.git', branch: 'master', credentialsId: 'muntaser4github')
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
