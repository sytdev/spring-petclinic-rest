
pipeline {
    agent any

    tools{
        maven 'maven3.8.8'
    }

    stages{
        
        stage("Compile"){
            
            steps {
                sh 'mvn clean compile -B -ntp'
            }
        }

        stage("Test"){
            steps {
                sh "mvn test -B -ntp"
                junit "target/surefire-reports/*.xml"
                jacoco()
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package -DskipTests -B -ntp'
            }
        }

    }

    // post{
    //     always{
    //         cleanWs()
    //     }
    // }
}
11