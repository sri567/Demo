pipeline{
agent any
  environment{
    PATH="/opt/apache-maven-3.6.3/bin:$PATH"
  }
  stages{
    stage("mavn war file"){
      steps{
       sh ''' mvn package '''
      }
    }
    
    
    
    stage("tomcat stop") {
      steps{
        
        sh ''' sudo /opt/apache-tomcat-8.5.65/bin/shutdown.sh '''
      }
    }
    
    
    
    stage("tomcat -deploy"){
      steps{
     sh ''' sudo cp /var/lib/jenkins/workspace/Demo/target/demoart.war /opt/apache-tomcat-8.5.65/webapps/ '''

      }
      }
    
    stage("tomcat start") {
      steps{
        
        sh ''' sudo /opt/apache-tomcat-8.5.65/bin/startup.sh '''
      }
    }
    
  }
}
