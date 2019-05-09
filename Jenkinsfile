pipeline {
    agent any
    environment {
        GITHUB_CREDS = credentials('GITHUB_USER')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "Github User: ${GITHUB_CREDS_USR}"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'true'
            }
        }
        stage('Deploy') {
            when {
              expression {
                currentBuild.result == null || currentBuild.result == 'SUCCESS' 
              }
            }
            steps {
                echo 'Deploying....'
            }
        }
    }
}
