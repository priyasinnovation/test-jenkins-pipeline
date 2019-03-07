pipeline {
  agent any
  stages {

      stage('Checkout') {
      steps {
          checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: ${remoteurl}]]])
        }
      }
      stage ('Build') {
      steps {
          sh script: 'mvn clean install'
        }
      }
      stage('Deploy-pushes to nexus') {
      steps {
          sh script: 'mvn clean deploy -DskipTests=true'
        }
      }
  }

  post {
      success {
          office365ConnectorSend message:"Build Success", status:"SUCCESS", webhookUrl:"${webhookurl}", color: "05b222"
       }

      failure {
          office365ConnectorSend message:"Build Failed in Jenkins", status:"FAILED", webhookUrl:"${webhookurl}", color: "d00000"
      }

  }

}



