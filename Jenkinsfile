node
{
  stage ('SCM-Checkout')
  {
    git 'https://github.com/ramdevops03/maven-build'
  }
  stage ('Compile-Package')
  {
    def mvnHome = tool name: 'TestJenkinsMaven', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
}
