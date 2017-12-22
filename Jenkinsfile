pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        staqge('Deploy to Staging') {
            steps {
                build job: 'deploy-to-staging'
            }
        }
    }
}