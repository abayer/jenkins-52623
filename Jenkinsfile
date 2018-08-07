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
        sh 'echo Outside container: GIT_BRANCH is ${GIT_BRANCH}'
        container('maven') {
          sh 'echo In container: GIT_BRANCH is ${GIT_BRANCH}'
	}
      }
    }
  }
}
