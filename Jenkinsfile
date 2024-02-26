
pipeline{
    
  
    agent any
    
    stages{

      stage('clone Repo')
      {
        steps{
              git branch: 'nodejs', url: 'https://github.com/Sonal0409/MultiBranchDeployment.git'
        }
      }

        stage('Build Image')
        {
            steps{
                sh 'docker build -t myappnodejs:$BUILD_NUMBER .'
            }
        }
        
        stage('Deploy the Image')
        {
            steps{
                sh 'docker run -d -P myappnodejs:$BUILD_NUMBER'
                sh 'docker ps'
            }
        }
        
    }
    
}
