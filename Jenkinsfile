pipeline{
   agent any
   tools{
       maven 'Maven'
   }
   stages{
       stage('Checkout'){
            steps{
                 git branch:'master' ,url:'https://github.com/PSS004/rajmav1.git'
             }
       }
       stage('Build'){
            steps{
                 sh 'mvn clean package'
             }
       }
       stage('Test'){
            steps{
                 sh 'mvn test'
             }
       }
       stage('Run Application'){
            steps{
                 sh 'java -jar target/maven55-1.0-SNAPSHOT.jar'

             }
       }  
    }
    post{
        success{
             echo 'Build and deploy successful'
        }
        failure{
             echo 'Build failure'    
        }
   }
} 
