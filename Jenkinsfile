pipeline {
    agent any
    tools {
        maven "maven-main-nodo"
    }
    stages {
	    stage('Build') {
	        steps {
	            dir ('projects-jenkins') {
	              sh 'mvn -DskipTests clean package'
	            }
	        }
	    }
    }
    post {
        success {
            dir ('project-jenkins') {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
