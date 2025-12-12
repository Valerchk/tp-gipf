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
          -Dsonar.host.url=${env.SONAR_HOST_URL} \
          -Dsonar.login=${env.SONAR_AUTH_TOKEN}
      """
    }
  }
}
