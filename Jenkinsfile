pipeline {

  agent {
    label 'maven'
  }

  stages {
  
    stage('Deploy') {
      steps {
        echo 'Deploying...Salman Mesam Ali.'
        script {

          openshift.withCluster() { 
  openshift.withProject("8dfoodh-dev") { 
    def deployment = openshift.selector("dc", "backend-salman-7000") 
    
   if(!deployment.exists()){ 
      openshift.newApp('backend-salman-7000', "--as-deployment-config").narrow('svc').expose() 
    } 
    
    timeout(2) { 
      openshift.selector("dc", "backend-salman-7000").related('pods').untilEach(1) { 
        return (it8dfoodh-devhase == "Running") 
      } 
    } 
  } 
}

        }
      }
    }
  }
}
