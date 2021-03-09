pipeline 
{ environment {
    registry1 = "jarrayaahmed99/frontimage"
    registry2 = "jarayaahmed99/backimage"
    DockerCredentials = 'dockerhub'
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
      
      
      
      
      
       
    
                
  
     stage("Build image angular") {
            steps {
                script {
                    
                    angular= docker.build(registry1+":${env.BUILD_ID}", "-f ${env.WORKSPACE}/angular-app/Dockerfile .")
                                             
                }
            }
        }
      
      stage("Build image express") {
            steps {
                script {
                    
                    express= docker.build(registry2+":${env.BUILD_ID}", "-f ${env.WORKSPACE}/express-server/Dockerfile .")
                                             
                }
            }
        }
    stage ("push angular image to dockerhub")
      { steps {
              script {
          docker.withRegistry( '', DockerCredentials) {
            angular.push(env.BUILD_ID)
            angular.push("latest")
             }
             }
          }
        stage ("push express image to dockerhub")
      {
          steps {
              scritpt
             {
          docker.withRegistry( '', DockerCredentials ) {
            express.push(env.BUILD_ID)
            express.push("latest")
             }
             }
          }
    
    
    
  
  }
      }
  }
}
