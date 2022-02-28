pipeline {
  agent {
    kubernetes {
      yamlFile 'KubernetesPod.yaml'
    }
  }
  environment {
	  DOCKER_REGISTRY_CREDS = credentials('Docker-Registry')
  }  	
  stages {  
    stage("Build & Push") {
        steps {
            container('kaniko') {
              sh 'ls'
        }
        }
        }  	  
  }
}
