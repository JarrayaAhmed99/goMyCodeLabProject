pipeline 
{ environment {
    registry1 = "jarrayaahmed99/frontimage"
    registry2 = "jarayaahmed99/backimage"
    registryCredential = 'dockerhub'
    angular= ''
    express= ''
    
              }

  agent any

  stages {
    


    stage('Checkout Source')
    {
      steps {
        git url:'https://github.com/JarrayaAhmed99/goMyCodeLabProject.git', branch:'main'
            }
    
    }
          stage('pwd')
    {
      steps {
        sh'pwd'
            }
        
    }
         
   
             stage('lsah')
    {
      steps {
        sh'ls -ah'
            }
        
    }
      
      
      
             stage('sleep')
    {
      steps {
        sh'sleep 60000'
            }
        
    }
      
      
       
    
                
  
     stage("Build image") {
            steps {
                script {
                    
                    angular= docker.build(registry1+":${env.BUILD_ID}", "-f ${env.WORKSPACE}/angular-app/Dockerfile .")
                                             
                }
            }
        }
      
      stage("Build image express") {
            steps {
                script {
                    
                    express= docker.build(registry2+":${env.BUILD_ID}", "-f ${env.WORKSPACE}/angular-app/Dockerfile .")
                                             
                }
            }
        }
    
    
    
    
    
  
  }

}
