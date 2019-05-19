pipeline {
    agent any

    stages {
     	stage ('Init') {
            steps {
                echo "Init result: ${currentBuild.result}"
                echo "Init currentResult: ${currentBuild.currentResult}"
            }
            post {
                always {
                    echo "Post-Init result: ${currentBuild.result}"
                    echo "Post-Init currentResult: ${currentBuild.currentResult}"
                	}
                }
        }
        stage('Build') {
            steps {
                withMaven(maven: 'maven_3_0_5') {
					sh 'mvn clean compile'
                }
            }
        }
        stage('Test') {
	        steps {
	      	  withMaven(maven: 'maven_3_0_5') {
	 				sh 'mvn test'
	 			}
            }
        }
        stage('Deploy') {
            steps {
              //  if(${currentBuild.currentResult} == "SUCCESS" || ${currentBuild.currentResult} == "UNSTABLE"){
			  //    if (isUnix()) {
				sh 'echo "Build Succeded."'
			        sh 'mvn clean package'
			//	      }else{
			//	        bat 'echo "Build Succeded."'
			//	      }
		   //  	}
            }
        }
    }
}

