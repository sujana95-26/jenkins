pipeline {
  agent any
  stages {
    stage('Clean up'){
      steps {
        sh "docker rm -f \$(docker ps -aq) || true"
      }
    }
    stage('build stage'){
      steps {
        sh "docker build -t myapp ."
      }
    }
    stage('test stage'){
      steps {
        sh "docker run -d -p 80:5500 --name app myapp" 
      }
    }
  }
}
