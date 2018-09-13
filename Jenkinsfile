node {
    stage('checkout') {
        git 'https://github.com/ryanwrencbtest/canary-app.git'
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
