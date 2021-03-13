pipeline 
{ environment {
    registry1 = "jarrayaahmed99/frontimage"
    registry2 = "jarayaahmed99/backimage"
    registryCredential = 'dockerpassword'
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
                    
                    angular= docker.build(registry1 , "-f ${env.WORKSPACE}/angular-app/Dockerfile .")
                                             
                }
            }
        }
      
      stage("Build image express") {
            steps {
                script {
                    
                    express= docker.build(registry2 , "-f ${env.WORKSPACE}/express-server/Dockerfile .")
                                             
                }
            }
        }
    stage ("pushing angular image to dockerhub")
      { steps {
              script {
          docker.withRegistry( '', registryCredential) {
            angular.push(env.BUILD_ID)
            angular.push("latest")
             }
             }
          }
      }
        stage ("pushing express image to dockerhub")
      {
          steps {
              script
             {
          docker.withRegistry( '', registryCredential) {
            express.push(env.BUILD_ID)
            express.push("latest")
             }
             }
          }
      }
    
    
    
  
  }
      } 

