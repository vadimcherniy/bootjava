pipeline {
  agent any
  stages {
    stage('gitCheckout') {
      steps {
        git(url: 'https://github.com/vadimcherniy/bootjava.git', branch: 'master')
      }
    }

    stage('build') {
      steps {
        sh '''java --version
git --version'''
      }
    }

  }
}