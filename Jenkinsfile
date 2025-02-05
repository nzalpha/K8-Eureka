
pipeline{
    agent{
        label 'workernode-1'
    }

    tools{
        maven 'mvn-3.8.8'
        jdk 'jdk-17'
    }
    environment {
        Application_Name = "eureka"
        Pom_Version = readMavenPom().getVersion()
        Pom_Packaging=readMavenPom().getPackaging()
    }
    stages{
        stage ('Build'){
            // This will take care of building the application
            steps{
                echo "Building ${env.Application_Name} Application"
                // build using maven
                sh 'mvn clean package -DskipTests=true'
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }

        /*stage ('Unit Tests'){
            steps {
                echo "Executing Unit Tests for ${env.Application_Name} App"
                sh 'mvn test'
            }
        } 
        */

        stage ('Docker Format'){
            steps{
                //install Pipeline Utility to use readMavenPOM
                //i27-eureka-0.0.1-SNAPSHOT.jar →> eureka-build number-branch name.jar
                echo "The actual format is ${env.Application_Name}-${env.Pom_Version}.${env.Pom_Packaging}"

            }
        }
    }
}