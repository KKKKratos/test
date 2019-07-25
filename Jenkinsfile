pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'cnpm install'
        sh 'cnpm run build'
      }
    }
  }
}