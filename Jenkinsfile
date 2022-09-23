node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'M2_HOME';
    withSonarQubeEnv() {
      sh "${mvn}/opt/maven clean verify sonar:sonar -Dsonar.projectKey=project-test"
    }
  }
}
