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
            container('maven') {
                script {
                    sh "mvn --version"
                }
            }
       }
    }
  }
}
