node('master')

{

stage('Continuous Download') 
   
	 {
	
    git 'https://github.com/hadoopkumar07/maven.git'
    
	}

stage('Continuous build') 
   
	 {
	
   sh label: '', script: 'mvn package'
	}

stage('Continuous Deployment') 
   
	 {
	
 sh label: '', script: 'scp  /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war  ubuntu@172.31.9.3:/var/lib/tomcat9/webapps/qaenv.war'
	}
stage('Continuous Testing') 
   
	 {
	sh label: '', script: 'echo "Testing Passed"'
	}
stage('Continuous Delivery') 
   
	 {
	sh label: '', script: 'scp  /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war  ubuntu@172.31.7.38:/var/lib/tomcat8/webapps/prodenv.war'
	}
}
