node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv('SonarScanner') {
      sh "./gradlew sonarqube -Dsonar.host.url=${http://localhost:9000/} -Dhttp.proxyHost=proxy1-rech -Dhttp.proxyPort=3128"
    }
  }
}
