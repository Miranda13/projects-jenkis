pipeline {
    agent any
    tools {
        maven "maven-main-nodo"
    }
    stage('Build') {
        steps {
            dir (‘maven-adderapp’) {
              sh 'mvn -DskipTests clean package'
            }
        }
    }
    post {
        success {
            dir (‘maven-adderapp’) {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
