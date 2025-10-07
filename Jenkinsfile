pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'git@github.com:twk1010/labtest.git'
            }
        }

        stage('print text') {
            steps {
                bat 'type file.txt'
            }
        }
    }
    post {
        success {
            echo 'Build was successful!'
            bat 'echo Build was successful! > success.txt'
        }

        failure {
            echo 'Build failed!'
            bat 'echo Build failed! > failed.txt'
        }

        always {
            echo 'Recording build timestamp...'
            bat 'echo %date% %time% > always.txt'
        }
    }
}
