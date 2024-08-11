
pipeline {
    //Forma 1: Ejecuta desde cualquier nodo
    //agent any
    //Usar el maven de los tools de Jenkins previamente configurado desde su interfaz
    // tools{
    //     maven 'maven3.8.8'
    // }

    //Forma 2: Ejecutar el pipeline desde un contenedor con maven
    agent{
        docker{
           image "maven:3.8.8-eclipse-temurin-17-alpine" 
        }
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

    post{
        always{
            cleanWs()
        }
    }
}