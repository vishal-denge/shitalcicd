node {
    stage ('Git Pull')
     
     {
       sh 'echo "git pull github repository"'
       git branch: 'main', changelog: true, credentialsId: 'vishal-denge', poll: false, url: 'https://github.com/vishal-denge/shitalcicd'
     }	
     

     stage ('Docker Build')
     
     {
       sh 'docker build -t shitalcicd:${BUILD_NUMBER} .'
	   sh 'docker tag shitalcicd:${BUILD_NUMBER} vishaldenge/shitalcicd:${BUILD_NUMBER}'
     }
     
     stage ('DOCKER PUSH')
     
     {
       sh "docker login -u vishaldenge -p 'v!sh@l123'"
       sh 'docker push vishaldenge/shitalcicd:${BUILD_NUMBER}'
     }
     
     
}
