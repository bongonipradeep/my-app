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
  stage ('Deploy')
  {
    sh "sudo cp web.war /root/apache-tomcat-8.5.85/webapps"
    
  }
}
