pipeline {
	agent {label 'master'}
 
	stages {
		stage ('Make and Maven') {
			parallel {
				stage ('makefile') {
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
					steps {
						echo 'This is slaveforc node with STAGE 1'
						sh '''
							if [[ -d "./mainrepo" ]]; then 
								cd "./mainrepo" && git pull
								mvn clean install 
							else 
								git clone https://github.com/manu289/hello-world.git
								cd "./mainrepo" && mvn clean install
							fi
						'''
					}	
				}
			}
		}
	}
}
