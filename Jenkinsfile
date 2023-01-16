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
						//def files = findFiles(glob: '*/*.json*')
						//PROJECT_JSON = files[0].path
						//println("$PROJECT_JSON")
						
						def foldersList = []
                    
						def osName = isUnix() ? "UNIX" : "WINDOWS"
						echo "osName: " + osName
					
						echo ".... JENKINS_HOME: ${WORKSPACE}"
					
						if(isUnix()) {
							def output = sh returnStdout: true, script: "ls -l ${WORKSPACE} | grep ^d | awk '{print \$9}'"
							foldersList = output.tokenize('\n').collect() { it }
						} else {
							def output = bat returnStdout: true, script: "dir '*project.json'"
							foldersList = output.tokenize('\n').collect() { it }
							foldersList = foldersList.drop(2)
									
						}
						echo ".... " + foldersList
 
 
					}
	            }
	        }

	    }
	}
