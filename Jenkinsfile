node{
      def mvnHome = tool name: 'maven 3.5.4', type: 'maven' 
      stage('Checkout'){
            echo 'checkout stage...'
         git 'https://github.com/LovesCloud/java-tomcat-maven-example'
       
      }  
      stage('Build'){
         //// Get maven home path and build
        echo 'build stage...'
        sh 'mvn -version'    
        sh "${mvnHome}/bin/mvn clean package -Dmaven.test.skip=true"
      }
     stage ('Test-JUnit'){
           echo 'test stage...'
         sh "'${mvnHome}/bin/mvn' test surefire-report:report"
      }  
    
      stage('Deploy') {   
            echo 'deploy stage...'
           /*sshagent(['Tomcat-jenkins']) {
               sh 'scp -o StrictHostKeyChecking=no target/tomcatdeploymnetdemo.war jenkins@35.193.54.220:/opt/tomcat/webapps'
          }*/
     }
      
 }
