node {
    stage('Checkout') {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/priyasinnovation/test-jenkins-pipeline.git']]])
    }
    stage ('Build') {
        sh label: '', script: 'mvn clean install'
    }
}