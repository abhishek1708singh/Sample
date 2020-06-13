node{
  stage('SCM Checkout'){
    git 'https://github.com/abhishek1708singh/Sample';
  }
  stage('Compile-package'){
  //get maven home path
  def mvnHome=tool name: 'maven3', type: 'maven'
    sh "$(mvnHome)/bin/mvn package;
  }
}
