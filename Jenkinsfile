
pipeline {
    agent any

    tools{
        maven 'maven3.8.8'
    }

    stages{
        
        stage("Build"){
            
            steps{
                
                sh "mvn clean package -DskipTests -B -ntp"
            }
        }


    }
}
