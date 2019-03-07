node {
    def mvnHome
    stage('Checkout') {
        git 'https://github.com/priyasinnovation/test-jenkins-pipeline.git'
        mvnHome = tool 'M3'
    }
    stage ('Build') {
        sh "'${mvnHome}/bin/mvn'" clean install
    }
}