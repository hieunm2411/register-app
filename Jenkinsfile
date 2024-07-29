pipeline{
    agent{
        label "Jenkins-Agent"
    }
    tools{
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage("Cleanup Workspace"){
            steps{
                cleanWS()
            }
        }

        stage("Checkout From SCM"){
            steps{
                git branch: 'main', credentialsId: 'Github', url: 'https://github.com/hieunm2411/register-app'
            }
        }

        stage("Build Application"){
            steps{
                sh "mvn clean package"
            }
        }

        stage("Testing Application"){
            steps{
                sh "mvn test"
            }
        }
    }
}