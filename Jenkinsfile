pipeline
{
    agent any
    stages
    {
        stage('contDownload')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/maven.git'
            }
        } 
	stage('ContBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('contDeployment')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/declarativepipeline1/webapp/target/webapp.war ubuntu@172.31.39.5:/var/lib/tomcat10/webapps/three.war'
            }
        }
	stage('ContTesting')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/FunctionalTesting.git'
            }
        }
        stage('ContDelivery')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/declarativepipeline1/webapp/target/webapp.war ubuntu@172.31.37.98:/var/lib/tomcat10/webapps/four.war'
            }
        }
    }
}
