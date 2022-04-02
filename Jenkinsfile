pipeline {
  agent any
  triggers {
          githubPush()
      }
  tools {
    maven 'M3'
  }
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/vadimcherniy/bootjava.git', branch: 'master')
      }
    }
    stage('build') {
       steps {
            script {
                    sh "mvn clean package"
            }
       }
    }
  }
}
