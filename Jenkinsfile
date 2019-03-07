node {
    stage('Checkout') {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/priyasinnovation/test-jenkins-pipeline.git']]])
    }
    stage ('Build') {
        sh label: '', script: 'sudo /Users/pshivr1/Desktop/development/libs/apache-maven-3.5.4/bin/mvn clean install'
    }
}