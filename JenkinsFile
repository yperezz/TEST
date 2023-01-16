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
					def files = findFiles(glob: '**project.json**')
					PROJECT_JSON = ${files[0].path}	
	            }
	        }

	    }
	}