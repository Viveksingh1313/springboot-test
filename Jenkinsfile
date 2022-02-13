node {
    stages {
      stage('SCM') {
        checkout scm
      }
      stage('unit test') {
        steps {
          sh 'mvn clean test'
        }
      }
      stage('SonarQube Analysis') {
        def mvn = tool 'mvn';
        withSonarQubeEnv() {
          sh "${mvn}/bin/mvn sonar:sonar"
        }
      }
    }
}
