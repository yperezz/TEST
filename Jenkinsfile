pipeline {
	    agent any
		environment{
			PROJECT_JSON = ''
		}
	
	    stages {

	         // Build Stages
	        stage('Find File') {
	            steps {
	                echo "Building..with ${WORKSPACE}"
					script{
						//def files = findFiles(glob: '*enkins*')
						//PROJECT_JSON = files[0].path
						//println("$PROJECT_JSON")
						
						dir("$WORKSPACE") {
							def files = findFiles() 
							
							files.each{ f -> 
								if(f.directory) {
									echo "This is directory: ${f.name} "
								}
							}
						}
 
 
					}
	            }
	        }

	    }
	}
