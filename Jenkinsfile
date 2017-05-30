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
            
          },
          "Checkout-2": {
            git(url: 'https://github.com/vairamuthu-shanmugaraj/spring-mvc-showcase.git', branch: 'master')
            
          }
        )
      }
    }
    stage('build') {
      steps {
        sh 'ls'
        sh '''mvn clean install
ls'''
      }
    }
    stage('war-component') {
      steps {
        sh '''ls
cd target/
ls'''
      }
    }
    stage('Deployment') {
      steps {
        input(message: 'input', id: 'ip', ok: 'ok')
        sh '''cp $WORKSPACE/target/*.war /home/ubuntu/apache-tomcat-9.0.0.M21/webapps/
sleep 30
curl localhost:8080/StudentEnrollmentWithSpringWebApp15.0-SNAPSHOT'''
      }
    }
  }
}