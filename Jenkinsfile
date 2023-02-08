pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/devopsdeepdive/blueocean-test-repo.git', branch: 'master', credentialsId: 'github-user')
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
 stage('Deploy') {
      steps {
        ssshagent(['tomcat_server']) {
sh  'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/-teavm-maven-webapp/target/teavm-maven-webapp-1.0-RELEASE.war ubuntu@172.31.0.57:/opt/apache-tomcat-8.5.85/webapps'
}
      }
    }
  }
}

