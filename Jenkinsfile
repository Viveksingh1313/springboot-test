pipeline {
    agent any
    stages {
      stage('HelloWorld') {
        steps {
          echo 'Hello World'
        }
      }
      stage('git clone') {
        steps {
          git url: 'https://github.com/Viveksingh1313/springboot-test.git'
        }
      }
      stage('unit test') {
        steps {
          sh 'mvn clean test'
        }
      }
//       stage('SonarQube Analysis') {
//         def mvn = tool 'mvn';
//         withSonarQubeEnv() {
//           sh "${mvn}/bin/mvn sonar:sonar"
//         }
//       }
    }
}
