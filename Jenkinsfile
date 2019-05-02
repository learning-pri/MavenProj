pipeline {
	 agent any
	 
	 stages ('Compile Stage') {
		 steps {
		 		withMaven (maven : 'maven_3_0_5') {
		 			sh 'mvn clean compile'
		 		}
		 	}
		}
	
	 stages ('Testing Stage') {
	 steps {
	 		withMaven (maven : 'maven_3_0_5') {
	 			sh 'mvn test'
	 		}
	 	}
	}
	
	 stages ('Deployment Stage') {
	 steps {
	 		withMaven (maven : 'maven_3_0_5') {
	 			sh 'mvn clean package'
	 		}
	 	}
	}
}