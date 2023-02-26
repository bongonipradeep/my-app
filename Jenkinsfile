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
  
    
  stage ('nexus upload')
  {
    sh "nexusArtifactUploader artifacts: [[artifactId: 'web', classifier: '', file: 'target/web.war', type: 'war']], credentialsId: '55a80184-88c6-4b21-989d-32079a15e09b', groupId: 'project', nexusUrl: '54.89.202.254:8081/nexus', nexusVersion: 'nexus2', protocol: 'http', repository: 'releases', version: '2.3'"

  }
  
  stage ('Deploy')
  {
    sh "ls -lrt"
    sh "sudo rm -rf /root/apache-tomcat-8.5.85/webapps/web.war"
    sh "sudo cp target/web.war /root/apache-tomcat-8.5.85/webapps"
  }
}
