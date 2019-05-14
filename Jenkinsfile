pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
	        steps {
	 			sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'mvn clean package'
                sh 'cd target'
                sh 'cp target/MavenProj-0.0.1-SNAPSHOT.jar /tmp/'
            }
        }
    }
}

