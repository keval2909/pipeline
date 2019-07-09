node{
   stage('SCM Checkout'){
     git 'https://github.com/javahometech/my-app'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'Maven', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   stage('Deploy to Tomcat'){
   }
      
      sshagent(['keval']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@3.89.90.86:/home/ec2-user/apps/tomcat/apache-tomcat-9.0.21/webapps/'
}
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Hi Welcome to jenkins email alerts
      Thanks
      keval''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'kevalpra1994@gmail.com'
   

}
