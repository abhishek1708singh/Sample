node{
  stage('SCM Checkout'){
    git 'https://github.com/abhishek1708singh/Sample'
  }
  stage('Compile-package'){
  def mvnHome=tool name: 'maven3', type: 'maven'
    sh "${mvnHome}/bin/mvn package";
  }
  stage('Deploy war file to tomcat'){
  	 sshagent(['tomcat-dev']) {
    sh 'scp -o StrictHostKeyChecking=no target /*.war ec2-user@<public_ip_of_EC2>:/opt/tomcat8/webapps/'
		}
  }
}
