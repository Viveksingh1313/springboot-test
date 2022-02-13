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
          git branch: 'dev', url: 'https://github.com/Viveksingh1313/springboot-test.git'
        }
      }
      stage('unit test') {
        steps {
          sh 'mvn clean test'
        }
      }
      stage('SonarQube Analysis') {
        steps {
            //def mvn = tool 'mvn';
            withSonarQubeEnv('sonarqube') {
                sh "mvn sonar:sonar"
            }
            timeout(time: 10, unit: 'MINUTES') {
                waitForQualityGate abortPipeline: true
            }
        }
      }
    }
}
