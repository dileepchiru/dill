node('master') 
{
   stage('ContnuousDownload') 
   {
      git 'https://github.com/thrinadhp/maven.git'
   }
   stage('ContnuousBuild') 
   {
      sh label: '', script: 'mvn package'
   }
   stage('ContinuousDeployment')
   {
       sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.46.166:/var/lib/tomcat8/webapps/qaenv.war'
   }
   stage('ContinuousTesting')
   {
       git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
   }
   stage('ContinuousDelivery')
   {
       sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.38.152:/var/lib/tomcat8/webapps/prodenv.war'
   }
   
   
   
   
   
   
   
   
   
   
   
}
