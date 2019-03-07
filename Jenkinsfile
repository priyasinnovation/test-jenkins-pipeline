node {
    def mvnHome
    stage('Checkout') {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/priyasinnovation/test-jenkins-pipeline.git']]])
    }
    stage ('Build') {
        mvnHome = tool 'M3'
        sh "'${mvnHome}/bin/mvn'" clean install
    }
}