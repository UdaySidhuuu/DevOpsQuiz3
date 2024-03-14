pipeline {
    agent any

    triggers {
        cron('H/10 * * * 4')
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Build the project (assumes Maven is used)
                    bat 'mvn clean package'
                }
            }
        }
        stage('Generate JaCoCo Report') {
            steps {
                script {
                    // Generate JaCoCo code coverage report
                    bat 'mvn test jacoco:report'
                }
            }
        }
    }
}
