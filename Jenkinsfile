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
         stage('Complile') {
            steps {
                sh 'mvn clean complile'
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
         stage('Install') {
            steps {
                sh 'mvn install'
            }
        }
    }
}
