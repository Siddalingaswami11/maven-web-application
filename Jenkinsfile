node {
    def mavenHome = tool name: "maven3.9.6"
    
    stage("check out code") {
        git credentialsId: '95e7f1c4-8f28-4d21-93ba-b3f9296e040d', url: 'https://github.com/Siddalingaswami11/maven-web-application.git'
    }
    
    stage("build the code") {
        sh "${mavenHome}/bin/mvn clean package"
    }
    
    stage("execute the SonarQube analysis") {
        sh "${mavenHome}/bin/mvn clean sonar:sonar" 
    }
    
    /*
    stage("upload the artifact into artifactory repository") {
        sh "${mavenHome}/bin/mvn clean deploy" 
    }
    
    stage("Deploy the app into Tomcat server") {
        sshagent(['Tomcatpass']) {
            sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@43.205.255.70:/opt/apache-tomcat-8.5.99/webapps/"
        } 
    }
*/
}
