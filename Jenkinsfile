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
            echo "user logged in ${user}"
          }
        }

        stage('test logs') {
          steps {
            echo 'test logs'
            writeFile(file: 'test-logs.txt', text: "testing logs for user ${user}")
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
            archiveArtifacts 'test-logs.txt'
          }
        }

      }
    }

  }
  environment {
    user = 'Dilip Meghwal'
  }
}