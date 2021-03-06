pipeline 
{ environment {
    registry = "jarrayaahmed99/projet"
    registryCredential = 'dockerhub'
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
                    
                    def front = docker.build("gomycodelabproject_angular:${env.BUILD_ID}")
                                             
                }
            }
        }
    
    
    
    
    
  
  }

}
