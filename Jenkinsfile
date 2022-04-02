pipeline {
  agent any
  tools {
      maven 'M3'
    }
  stages {
    stage('gitCheckout') {
      steps {
        git(url: 'https://github.com/vadimcherniy/bootjava.git', branch: 'master')
      }
    }
    stage('build') {
      steps {
        sh 'mvn --version'
      }
    }

  }
}
