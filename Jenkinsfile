
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


    }
}