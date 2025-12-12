node {
  stage('SCM') {
    checkout scm
  }

  stage('Prepare') {
    sh 'chmod +x ./gradlew || true'
  }

  stage('SonarQube Analysis') {
    withSonarQubeEnv('SonarScanner') {
      sh """
        ./gradlew sonarqube \
          -Dsonar.projectKey=SonarTest \
          -Dsonar.projectName='SonarTest' \
          -Dsonar.host.url='http://localhost:9000' \
          -Dsonar.login='c9e130d4d6f3dc12066eb0aa990a1766d491674b'
      """
    }
  }
}
