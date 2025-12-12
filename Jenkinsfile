node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv('SonarScanner') {
      sh "./gradlew sonar -Dhttp.proxyHost=proxy1-rech -Dhttp.proxyPort=3128"
    }
  }
}
