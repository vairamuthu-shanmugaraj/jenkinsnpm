pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        parallel(
          "checkout": {
            git(url: 'https://github.com/vairamuthu-shanmugaraj/SampleStudentProject.git', branch: 'master')
            sh 'ls'
            
          },
          "echo": {
            echo 'helloo'
            
          }
        )
      }
    }
    stage('build') {
      steps {
        sh 'ls'
        sh '''cd SampleStudentProject
ls'''
      }
    }
  }
}