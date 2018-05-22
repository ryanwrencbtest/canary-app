node {
    //Testing this on a 2.89.1.7 AWS cluster!
    stage('checkout') {
        git 'https://github.com/ryanwren/devoptics-checkout.git'
    }
    stage ('build') {
        withMaven(maven: 'Maven350') {
            sh "mvn clean install"
        }
    }
    stage ('fingerprint') {
        archiveArtifacts artifacts: "target/*.jar", fingerprint: true
    }
}
