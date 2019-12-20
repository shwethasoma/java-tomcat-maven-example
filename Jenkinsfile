pipeline
{
  agent any
  stages
  {
    stage('Build Application')
    {
        steps
        {
           bat 'mvn -f java-tomcat-sample/pom.xml package'
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
