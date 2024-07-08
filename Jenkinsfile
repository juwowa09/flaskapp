pipeline {
    agent any
    environment {
        NEW_VERSION = '1.0.0'
    }
    stages {
        stage("build") {
            steps {
                echo 'building the application...'
                echo "building version ${NEW_VERSION}"
            }
        }
        stage("test") {
            steps {
                echo 'testing the application...'
            }
        }
        stage("deploy") {
            steps {
                echo 'deploying the application...'
                withCredentials([[$class: 'UsernamePasswordMultiBinding', 
                                  credentialsId: 'juwowa_admin_crendentials', 
                                  usernameVariable: 'juwowa_user', 
                                  passwordVariable: 'wn0605']]) {
                    sh 'printf ${USER}'
                }
            }
        }
    }
}
