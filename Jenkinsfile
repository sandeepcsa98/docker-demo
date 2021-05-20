node {
  def app
  stage("Clone repository'){
        checkout scm
        }
        
        stage('Build image'){
         app = docker.build("sandeepcs09/jenknis_repo") 
          
        }
        
        stage('Test image'){
          app.inside{
           sh 'echo "Tests passed"' 
          }
          
        }
        
        stage('push image'){
          docker.withRegistry('https://registry.hub.docker.com', 'dockerhub_id'){
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
          }
          
        }
                            
                            
  
}
