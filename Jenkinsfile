node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv('SonarScanner') {
      sh "./gradlew -Dhttp.proxyHost=proxy1-rech -Dhttp.proxyPort=3128"
      sh "./gradlew sonar \
  -Dsonar.projectKey=SonarTest \
  -Dsonar.projectName='SonarTest' \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.token=sqp_c9e130d4d6f3dc12066eb0aa990a1766d491674b"
    }
  }
}
