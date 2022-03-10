pipeline {
  agent {
    dockerfile true
  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            echo 'building the code'
            sh 'node -version'
            sh 'pwd'
          }
        }
      }
    }
  }
}
