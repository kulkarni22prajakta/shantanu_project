pipeline {
agent {
label {
		label "built-in"
		customWorkspace "/data/project-myapp"
		
		}
		}
		
	stages {
		
		stage ('CLEAN_OLD_M2') {
			
			steps {
				sh "rm -rf /home/prajakta/.m2/repository"
				
			}
			
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "mvn clean install -DinstallskipTetsts=true"
			
			}
			
		
		}
		
		stage ('deploy on docker container'){
		
				steps {
						
						sh "docker-compose up"

						}
				
				}
	
	
	
	}
		
}
