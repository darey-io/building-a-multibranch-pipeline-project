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
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
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
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
            }
        }

        stage('Deliver for HotFix') {
            when {
                branch 'hotfix*' 
            }
            steps {
                sh 'echo This is Dev'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
            }
        }


        stage('Deliver for Integration') {
            when {
                branch 'stage*' 
            }
            steps {
                sh 'echo This is Dev'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
            }
        }

        stage('Deploy for production') {
            when {
                branch 'master'  
            }
            steps {
                sh 'echo This is Production'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
            }
        }
    }
}