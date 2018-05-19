pipeline {
	agent any
	
	stages {
	
		stage ('Compile Stage') {
		
			steps {
				withMaven(maven : 'maven') {
					sh 'mvn clean install'
				}				
			} 
	    }
	    
		stage ('Testing Stage') {
		
			steps {
				withMaven(maven : 'maven') {
					sh 'mvn test'
				}				
			} 
	    }
	    
		stage ('Deploy') {
		
			steps {
				withMaven(maven : 'maven') {
					sh 'mvn clean package cargo:redeploy -P dev'
				}				
			} 
	    }	    	
	    
	}
}