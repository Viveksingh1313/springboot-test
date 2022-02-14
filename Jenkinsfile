pipeline {
    agent any
    stages {
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
            withSonarQubeEnv('sonar') {
                sh "mvn sonar:sonar"
            }
//             timeout(time: 4, unit: 'MINUTES') {
//                 waitForQualityGate abortPipeline: true
//             }
        }
      }
      stage('Build Jars') {
        steps {
            sh 'mvn -DskipTests clean package'
        }
      }
    }
}
