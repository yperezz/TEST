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
						
						    // Get all files from a directory.
							File directory = new File("$WORKSPACE");
							File[] fList = directory.listFiles();
							if(fList != null)
								for (File file : fList) {      
									if (file.isFile()) {
										files.add(file);
									} else if (file.isDirectory()) {
										listf(file.getAbsolutePath(), files);
									}
								}
								
							
							fList.each{ f -> 
								if(f.directory) {
									echo "This is directory: ${f.name} "
								}
							}
 
 
					}
			    
			    
			    
	            }
	        }

	    }
	}
