pipeline {
    agent any
    parameters {
        string(name: 'VERSION', defaultValue: '', description: 'deployment version')
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: false, description: 'Execute test stage')
    }
    stages {
        stage("build") {
            steps {
                echo 'building the application...'
            }
        }
        stage("test") {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo 'testing the application...'
            }
        }
        stage("deploy") {
            steps {
                echo "deploying version ${params.VERSION}..."
            }
        }
    }
}
