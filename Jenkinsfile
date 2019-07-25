pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'cnpm install'
        sh 'cnpm run build'
      }
    }
    stage('Deploy') {
      steps {
        sh '/root/downloads/build.exp'
      }
    }
  }
}