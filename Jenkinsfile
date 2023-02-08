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
sh ssh -o StrictHostKeyChecking=no 'scp /var/lib/jenkins/workspace/blueocean-test-repo_master/target/teavm-maven-webapp-1.1-SNAPSHOT.war ubuntu@ec2-3-112-58-132.ap-northeast-1.compute.amazonaws.com:/opt/apache-tomcat-8.5.85/webapps'
}
      }
    }
  }
}

