node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv() {
      sh "./gradlew sonar -D https.proxyHost=proxy1-rech -D https.proxyPort=3128"
    }
  }
}
