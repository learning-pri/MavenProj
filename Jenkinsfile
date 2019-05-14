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
                if(currentBuild.currentResult == "SUCCESS" || currentBuild.currentResult == "UNSTABLE"){
				    if (isUnix()) {
						sh 'echo "Build Succeded."'
				        sh 'mvn clean package'
       			        sh 'cd target'
                		sh 'cp target/MavenProj-0.0.1-SNAPSHOT.jar /tmp/'
				      }else{
				        bat 'echo "Build Succeded."'
				      }
		     	}
            }
        }
    }
}

