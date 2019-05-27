pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build . --tag testnode'
            }
        }
        stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
        stage('Deliver') {
            steps {
                sh 'docker run -d -p 80:8080 testnode'
            }
    	}
    }
}
