node {
    stage('checkout app a') {
        git 'https://github.com/ryanwrencbtest/canary-app.git'
    }
    stage ('build app a') {
        withMaven(maven: 'Maven350') {
            sh "mvn clean install"
        }
    }
    stage('checkout app b') {
        git 'https://github.com/ryanwrencbtest/canary-app-dev.git'
    }
    stage ('build app b') {
        withMaven(maven: 'Maven350') {
            sh "mvn clean install"
        }
    }
    stage ('fingerprint') {
        archiveArtifacts artifacts: "target/*.jar", fingerprint: true
    }
}
