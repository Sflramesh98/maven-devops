@Library("chandulibs") _
pipeline{
    agent any
    stages{
        stage("git checkout"){
            steps{
                git credentialsId: 'github-cred', url: 'https://github.com/chandrakala08/chandhusharedlibs.git'
                }
        }
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
