pipeline {
  agent any
  stages {
    stage('Build and Deploy') {
      steps {
        sh 'cnpm install'
        sh 'cnpm run build'
        sh '/root/downloads/build.exp'
      }
    }
  }
}