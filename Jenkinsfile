pipeline {
	agent none
 
	stages {
		stage ('Make and Maven') {
			parallel {
				stage ('makefile') {
					agent {label 'slaveforc'}
					steps { 
						echo 'This is makefile example'
						sh '''
							if [[ -d "./mainrepo" ]]; then 
								cd "./mainrepo" && git pull
								make 
							else 
								git clone https://github.com/manu289/mainrepo.git
								cd "./mainrepo" && make
							fi	
						'''
					}	
				}
				stage ('maven') {
					agent {label 'slaveforjava'}
					steps {
						echo 'This is maven example'
						sh '''
							if [[ -d "./hello-world" ]]; then 
								cd "./hello-world" && git pull
								mvn clean install 
							else 
								git clone https://github.com/manu289/hello-world.git
								cd "./hello-world" && mvn clean install
							fi
						'''
					}	
				}
			}
		}
	}
}
