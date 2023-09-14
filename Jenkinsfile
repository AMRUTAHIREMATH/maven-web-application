node{

echo "Jenkins Home dir is: ${env.JENKINS_HOME}"
echo "Job name is: ${env.JOB_NAME}"
echo "Build Number is: ${env.BUILD_NUMBER}"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'RebuildSettings', autoRebuild: false, rebuildDisabled: false], [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])

def mavenHome = tool name: 'maven3.9.3'

stage('CheckOutCode'){
git branch: 'development', credentialsId: '9bd48091-b016-4969-8e04-a5cd98d68c3a', url: 'https://github.com/AMRUTAHIREMATH/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}

stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}
}
*/

}
