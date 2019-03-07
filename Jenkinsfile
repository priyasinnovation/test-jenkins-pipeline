node {
    def mvnHome
    stage('Checkout') {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/priyasinnovation/test-jenkins-pipeline.git']]])
        mvnHome = tool 'M3'
    }
    stage ('Build') {
        sh "'${mvnHome}/bin/mvn'" clean install
    }
}