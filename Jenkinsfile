pipeline
{
  agent any
  stages
  {
    stage('Build Application')
    {
        steps
        {
           bat 'mvn  package'
        }
        post
        {
          success
          {
            echo "Now archiving the artifacts"
            archiveArtifacts artifacts:'**/*.war'
          }
        }
    }
    stage('Deploy in Staging Environment')
    {
        steps
        {
          build job:'Deploy_servlet_staging_env'
        }
    }
  }
}
