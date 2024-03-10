pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    build 'PES2UG21CS201-1'
                    sh 'g++ -o my_program task5.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './my_program'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy'
            }
        }
    }

    post {
        always {
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'Pipeline failed'
                }
            }
        }
    }
}

