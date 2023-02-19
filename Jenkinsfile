pipeline 
{
  agent any
  stages 
  {
    stage('Build') 
    {
      steps 
      {
        sh 'g++ main/cclab.cpp -o output'
        build 'PES2UG20CS900-1'
        echo 'PES2UG20CS900 - Build Stage Successful'
      }
    }
    stage('Test')
    {
      steps 
      {
        sh './output'
        echo 'PES2UG20CS900 - Test Stage Successful'
      }
    }
    stage('Deploy') 
    {
      when 
      {
        expression 
        {
          currentBuild.result = null || currentBuild.result == 'SUCCESS' 
        }
      }
      steps 
      {
        echo 'PES2UG20CS900 - Deployment Successful'
      }
    }
  }
  post 
  {
    failure 
    {
      echo 'PES2UG20CS900 - Pipeline failed'
    }
  }
}
