pipeline {
	agent none
 
	stages {
		stage ('makefile') {
			agent { label 'slaveforc' }
			steps { 
				git 'https://github.com/manu289/jenkins_pipeline.git'
		                 sh 'make'
				//*echo 'This is slaveforc node with STAGE 1'
				//sh 'sleep 10'
			}	
		}
		stage ('maven') {
			agent { label 'slaveforjava' }
			steps { 
				git 'https://github.com/manu289/jenkins_pipeline.git'
		                 sh 'mvn clean install'
				//*echo 'This is slaveforc node with STAGE 1'
				//sh 'sleep 10'
			}	
		}
		/*stage ('STAGE 3') {
			steps {
				echo 'This is slaveforc with STAGE 3'
				sh 'sleep 10'
			}	
		}
		stage ('STAGE 4') {
			steps {
				echo 'This is master with STAGE 4'
				sh 'sleep 10'
			}	
		}*/
	}
}
