pipeline {
    agent any
    environment {
        GITHUB_USER = credentials('GITHUB_USER')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo $GITHUB_USER
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
