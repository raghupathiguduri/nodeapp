pipeline {
    agent {
    	docker { 
	    image 'node:7-alpine'
	    args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
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
