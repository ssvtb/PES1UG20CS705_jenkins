pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'g++ -o cs705 cs705.cpp'
            }
        }

        stage('Test') {
            steps {
                sh './cs705'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deployed successfully'
            }
        }
    }

    post {
        always {
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'pipeline failed'
                }
            }
        }
    }
}
