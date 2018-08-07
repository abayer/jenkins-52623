pipeline {
  agent {
    kubernetes {
      label 'declarative-pod'
      containerTemplate {
        name 'maven'
        image 'maven:3.3.9-jdk-8-alpine'
        ttyEnabled true
        command 'cat'
      }
    }
  }
  stages {
    stage('Echo SCM env') {
      steps {
        container('maven') {
          sh 'echo GIT_BRANCH is ${GIT_BRANCH}'
	}
      }
    }
  }
}
