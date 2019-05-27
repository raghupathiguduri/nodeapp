pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build . --tag testnode'
            }
        }
        stage('Deliver') {
            steps {
                sh 'docker run -d -p 80:8080 testnode'
            }
    	}
    }
}
