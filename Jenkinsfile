pipeline {
    agent any
    tools {
        maven "M3"
    }
    stages {
        stage('test') {
            steps {
                sh "mvn clean test"
            }
            post {
                always {
                    junit '**/surefire-reports/TEST-*.xml'
                }
            }
        }
        stage('package') {
            steps {
                sh "mvn package -DskipTests"
            }
            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
                }
            }
        }
        stage('sonar analysis') {
            steps {
                withSonarQubeEnv(installationName: 'sq1') {
                    sh "mvn sonar:sonar"
                }
            }
        }
    }
}
