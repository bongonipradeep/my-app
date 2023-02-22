node
{
  stage ('SCM-Checkout')
  {
    git 'https://github.com/bongonipradeep/my-app'
  }
  stage ('Compile-Package')
  {
    sh 'mvn package'
  }
}
