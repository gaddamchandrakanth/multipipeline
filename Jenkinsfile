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
                sh 'scp /var/lib/jenkins/workspace/Jenkinsfile/webapp/target/webapp.war ubuntu@172.31.5.190:/var/lib/tomcat10/webapps/three.war'
            }
        }
	stage('ContTesting')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/FunctionalTesting.git'
		sh 'java -jar /var/lib/jenkins/workspace/Jenkinsfile/testing.jar'
            }
        }
        stage('ContDelivery')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/Jenkinsfile/webapp/target/webapp.war ubuntu@172.31.0.181:/var/lib/tomcat10/webapps/four.war'
            }
        }
    }
}
