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
		
		stage ('COPY_WAR_TO_Server'){
		
				steps {
						
						sh "cp -r target/LoginWebApp.war /mnt/apache-tomcat-9.0.78/webapps"

						}
				
				}
	
	
	
	}
		
}
