pipeline {
	agent any
 
	stages {
		stage ('Make and Maven') {
			parallel {
				stage ('makefile') {
					steps { 
						echo 'This is slaveforc node with STAGE 1'
						sh 'sleep 10'
					}	
				}
				stage ('maven') {
					steps {
						echo 'This is slaveforc node with STAGE 1'
						sh 'sleep 10'
					}	
				}
			}
		}
		stage ('STAGE 3') {
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
		}
	}
}
