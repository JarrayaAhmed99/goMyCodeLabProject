pipeline 
{ environment {
    registry = "jarrayaahmed99/projet"
    registryCredential = '9632587410Mawi'
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
                    myapp = docker.build("vamsijakkula/hellowhale:${env.BUILD_ID}")
                }
            }
        }
    
    
    
    
    
  
  }

}
