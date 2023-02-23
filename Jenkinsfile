node
{
  stage ('SCM-Checkout')
  {
    git 'https://github.com/ramdevops03/Development-Team-Repo.git'
  }
  stage ('Compile-Package')
  {
    def mvnHome = tool name: 'TestJenkinsMaven', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
}
