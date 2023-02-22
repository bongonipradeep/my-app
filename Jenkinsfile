node
{
  stage ('SCM-Checkout')
  {
    git 'https://github.com/bongonipradeep/my-app'
  }
  stage ('Compile-Package')
  {
    def mvnHome = tool name: 'TestJenkinsMaven', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
}
