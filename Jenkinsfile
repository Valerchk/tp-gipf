node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv('SonarScanner') {
      sh "./gradlew sonarqube -Dsonar.host.url=${env.SONAR_HOST_URL} -Dhttp.proxyHost=proxy1-rech -Dhttp.proxyPort=3128"
    }
  }
}
