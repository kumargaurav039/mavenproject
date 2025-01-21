pipeline
{
agent any
stages
{

stage ('scm checkout')
  { steps {  git branch: 'master', url: 'https://github.com/prakashk0301/mavenproject'   }}





stage('generate artifact and sonar analysis')



{ steps {withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
  { withSonarQubeEnv(credentialsId: 'sonar', installationName: 'sonar')
   {
    sh 'mvn clean install -DskipTests sonar:sonar'    
   }}  } }


 

}

}