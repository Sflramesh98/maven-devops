@Library("chandulibs") _
pipeline{
    agent any
    tools {
      maven 'maven3'
    }
    stages{
          stage("Maven Build"){
            steps{
                sh 'mvn clean package -DSkipTests=True'
            }
        }
        stage("Dev Tomcat Deploy"){
                        steps{
                            tomcatDeploy("172.31.41.206", "ec2-user", "tomcat-dev")
            }
        }
    }
}
