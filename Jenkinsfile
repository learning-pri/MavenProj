pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
	        steps {
	        	withMaven (maven : 'maven_3_0_5') {
		 			sh 'mvn test'
		 		}
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

