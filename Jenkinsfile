pipeline {
    agent any
    tools {
        maven 'maven3.8.8'
    }
    stages {
        /*
        stage('Checkout SCM') {
            steps {
                git branch: 'master', url: 'https://github.com/devops-mitocode/spring-petclinic-rest.git'
            }
        }
        */
        stage('Test') {
            steps {
                sh 'mvn clean test -B -ntp'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package -B -ntp'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            cleanWs()
        }
    }
    
}