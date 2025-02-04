
pipeline{
    agent{
        label 'workernode-1'
    }

    tools{
        maven 'mvn-3.8.8'
        jdk 'jdk-17'
    }

    stages{
        stage ('Build'){
            // This will take care of building the application
            steps{
                echo "Building Eureka Application"
                // build using maven
                sh 'mvn clean package -DskipTests=true'
            }
        }
    }
}