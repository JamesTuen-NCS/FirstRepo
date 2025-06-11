pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository containing the project
                git 'https://github.com/JamesTuen-NCS/FirstRepo'
            }
        }

        stage('Build') {
            steps {
                // Run Maven clean and package
                sh 'mvn clean package'
            }
        }

        stage('Teardown') {
            steps {
                // Run Maven teardown
                sh 'mvn teardown'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
