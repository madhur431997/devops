pipeline{
    agent any
    tools {
          jdk 'jdk'
        maven 'maven-3.5.4'
      
    }
    stages{
        stage("checkingout project"){
            steps{
                git credentialsId:'madhur_github' , url:'https://github.com/madhur431997/devops.git'
            }
        }
        stage ("compile"){
            steps{
                sh 'ls -lrt'
              
                sh 'mvn -f spring-boot-demo-master/pom.xml compile'
                
            }
        }
        stage ("code quality"){
            steps{
            withSonarQubeEnv ('sonar') {
                sh 'mvn -f spring-boot-demo-master/pom.xml clean install sonar:sonar'
            }        
                
            }
            }
         
        }
        
    }






