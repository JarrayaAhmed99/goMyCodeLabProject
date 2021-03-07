pipeline 
{ environment {
    registry1 = "jarrayaahmed99/frontimage"
    registry2 = "jarayaahmed99/backimage"
    registryCredential = 'dockerhub'
    angular= ''
    
              }

  agent any

  stages {
    


    stage('Checkout Source')
    {
      steps {
        git url:'https://github.com/JarrayaAhmed99/goMyCodeLabProject.git', branch:'main'
            }
    
    }
  
     stage("Build image") {
            steps {
                script {
                    
               angular= docker.build registry1 + ":$BUILD_NUMBER"
                                             
                }
            }
        }
    
    
    
    
    
  
  }

}
