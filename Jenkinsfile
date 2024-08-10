
pipeline {
    agent any

    tools{
        maven 'maven3.8.8'
    }

    stages{
        
        stage("Build"){
            
            steps{
                
                sh "mvn -f clean package -DskipTests -B -ntp"
            }
        }


    }
}
