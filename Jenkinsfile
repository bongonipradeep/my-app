node
{
  stage ('SCM-Checkout')
  {
    git 'https://github.com/ramdevops03/Development-Team-Repo.git'
  }
  stage ('Compile-Package')
  {
    def mvnHome = tool name: 'TestJenkinsMaven', type: 'maven'
    sh "${mvnHome}/bin/mvn clean"
    sh "${mvnHome}/bin/mvn package"
  }
  stage ('Deploy')
  {
    sh "ls -lrt"
    sh "sudo rm -rf /root/apache-tomcat-8.5.85/webapps/web.war"
    sh "sudo cp target/web.war /root/apache-tomcat-8.5.85/webapps"
  }
}
