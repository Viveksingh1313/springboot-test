pipeline {
    agent any
    tools {
        maven 'mvn'
        //version 3.0.5
    }
    parameters {
        choice(
            name: 'envSelected',
            choices: ['dev', 'test', 'prod'],
            description: 'Please choose en environment where you want to run?'
        )
    }
     stages {
//       stage('git clone') {
//         steps {
//           git branch: 'dev', url: 'https://github.com/Viveksingh1313/springboot-test.git'
//         }
//       }
          stage('unit test') {
            steps {
                echo "Environment selected: ${params.envSelected}"
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
                sh 'mvn clean package'
            }
          }
          stage('Run Spring Boot App') {
            steps {
                script {
                    if (env.envSelected == "dev" || env.envSelected == "test") {
                        echo 'triggered by dev or test'
                        ansiblePlaybook installation: 'ansible2', inventory: 'dev.inv', playbook: 'ansible.yml', disableHostKeyChecking: true
                    } else {
                        echo 'triggered by prod'
                        ansiblePlaybook installation: 'ansible2', inventory: 'dev.inv', playbook: 'ansible.yml', disableHostKeyChecking: true
                    }
                }

            }
          }
    }
}