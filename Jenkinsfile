pipeline{
    agent any
    tools {
       maven 'Maven'
    }
    stages{  
      stage("build.jar"){
        steps {  
          echo 'build the application'
           
        }
      }      
      stage("build image"){
        steps {
          echo 'test the docker image'
          whithVredentials(usernamePassword(credentialsid: 'docker_hub_cr', passwordVariable: 'PASS' , usernameVariable: 'USER'
          sh 'docker build -t oveeis/my-repo:2.0 . '
          sh "echo $PASS | docker login -u $USER --password-stdin" 
          sh 'docker push oveeis/my-repo:2.0'
        } 
      }      
      stage("deploy"){
        steps {  
          echo 'deploy the application'
        } 
      }        
    }                
}            
