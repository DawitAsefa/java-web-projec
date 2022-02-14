pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                step{
                   sh 'mvn clean package' 
                }
            }
            
        }
        
        stage('Deploy'){
            steps{
                step{
                   deploy adapters: [tomcat7(credentialsId: 'a4a763bb-cbf8-41bd-b9ce-73b617a22aec', path: '',
				   url: 'http://ec2-3-15-37-117.us-east-2.compute.amazonaws.com:8080/')], 
				   contextPath: 'javawebapp', war: '**/java-web-project.war'
                }
            }
            
        }
    }
}
