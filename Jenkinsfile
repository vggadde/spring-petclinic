pipeline {
    agent any
    stages {
        stage('Clean') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('Validate') {
            steps {
                sh 'mvn validate'
            }
        }        
         stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
         stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
         stage('SonarQube analysis') {
             steps {
          withSonarQubeEnv(credentialsId: 'sonar_token', installationName: 'local-sq') { // You can override the credential to be used
          sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
          }
         }
         }
        
         stage('Install') {
            steps {
                sh 'mvn install'
            }
        }
    }
}
