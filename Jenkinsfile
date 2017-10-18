pipeline {
  agent any
  stages {
    stage('Prepare'){
      steps{
        sh "echo this is prepare"
        sh "exit 1"
      }

    }
    stage('Clone') {
      steps {
        sh 'pwd'
        sh 'ls -l'
        git(url: 'https://github.com/chengjingtao/nodejs-ex2', branch: 'master', changelog: true, poll: true, credentialsId: 'abc')
        sh 'pwd'
        sh 'ls -l'
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
