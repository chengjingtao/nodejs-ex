pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git(url: 'https://github.com/chengjingtao/nodejs-ex', branch: 'master', changelog: true, poll: true)
      }
    }
    stage('Build') {
      steps {
        parallel(
          "Build": {
            sh 'echo "build"'
            
          },
          "Scan": {
            sh 'echo "scan code"'
            
          }
        )
      }
    }
    stage('Test') {
      steps {
        sh 'echo "test"'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "deploy"'
      }
    }
  }
}