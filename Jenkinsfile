node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv('SonarScanner') {
      sh "./gradlew -Dhttp.proxyHost=proxy1-rech -Dhttp.proxyPort=3128"
    }
  }
}
