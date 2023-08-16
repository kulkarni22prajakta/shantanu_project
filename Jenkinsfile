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
						sh "docker-compose exec mysql_container_name create database test;"
						sh "docker-compose exec mysql_container_name use test;"
						sh "docker-compose exec mysql_container_name CREATE TABLE `USER` (
  						`id` int(10) unsigned NOT NULL auto_increment,
 						 `first_name` varchar(45) NOT NULL,
						  `last_name` varchar(45) NOT NULL,
						  `email` varchar(45) NOT NULL,
						  `username` varchar(45) NOT NULL,
						  `password` varchar(45) NOT NULL,
						  `regdate` date NOT NULL,
						  PRIMARY KEY  (`id`));"
					}		
				}	
	}		
}
