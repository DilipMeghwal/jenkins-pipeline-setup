pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            echo 'building the code'
          }
        }

        stage('test') {
          steps {
            echo 'additional steps'
            echo '"user logged in ${user}"'
          }
        }

        stage('test logs') {
          steps {
            echo 'test logs'
          }
        }

      }
    }

    stage('deploy') {
      parallel {
        stage('deploy') {
          steps {
            echo 'deploying the code'
          }
        }

        stage('artifact') {
          steps {
            archiveArtifacts 'text-artifact.txt'
          }
        }

      }
    }

  }
  environment {
    user = 'Dilip Meghwal'
  }
}