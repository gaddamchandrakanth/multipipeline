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
     }
}
