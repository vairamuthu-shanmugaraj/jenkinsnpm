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
    stage('Building') {
      steps {
        readFile 'Jenkinsfile'
        timestamps() {
          sleep 10
        }
        
        build 'test2'
      }
    }
  }
}