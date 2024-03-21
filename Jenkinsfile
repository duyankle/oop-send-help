node {
  stage('SCM') {
    git branch: 'main', credentialsId: 'github', url: 'https://github.com/duyankle/oop-send-help.git'
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner -Dsonar.java.binaries=. -Dsonar.projectKey=oop-send-help Dsonar.login=sqa_105a88f9430d18e02058b51528ebc56c3c817162"
    }
  }
}
