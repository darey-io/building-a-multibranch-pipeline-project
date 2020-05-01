pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo This is building the code'
            }
        }
        stage('Test') {
            steps {
                sh 'echo This is testing the code'
            }
        }
        stage('Deliver for development') {
            when {
                branch 'dev*' 
            }
            steps {
                sh 'echo This is Dev'
            }
        }

        stage('Deliver for HotFix') {
            when {
                branch 'hotfix*' 
            }
            steps {
                sh 'echo This is Dev'
            }
        }


        stage('Deliver for Integration') {
            when {
                branch 'stage*' 
            }
            steps {
                sh 'echo This is Dev'
            }
        }

        stage('Deploy for production') {
            when {
                branch 'master'  
            }
            steps {
                sh 'echo This is Production'
            }
        }
    }
}