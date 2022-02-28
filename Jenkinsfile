pipeline {
  agent {
    kubernetes {	    
      label 'aqua-scanner'
      yamlFile 'KubernetesPod.yaml'
    }
  }	
  environment {
	  DOCKER_REGISTRY_CREDS = credentials('Docker-Registry')
  }  	
  stages {  
    stage("Scan") {
        steps {
	        container('scanner') {
            aqua locationType: 'hosted', registry: 'OCIR', hostedImage: 'fra.ocir.io/lolctech/fxapiuser/fusionx-base-image-jre:1.0.0', localImage: 'fra.ocir.io/lolctech/fxapiuser/fusionx-base-image-jre:1.0.0', policies: '',  notCompliesCmd: '', onDisallowed: 'ignore', hideBase: false, showNegligible: false, register: true, customFlags: '', localToken: Secret.fromString(""),containerRuntime: 'runc', scannerPath: '/opt/aquasec/'
        
       }
	   }
       }   	  
  }
}
