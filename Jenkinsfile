pipeline {
  agent any
  stages {
    stage('Clone code') {
      steps {
        git(url: 'https://github.com/oocl-kratos/test.git', branch: 'master', changelog: true)
      }
    }
  }
}