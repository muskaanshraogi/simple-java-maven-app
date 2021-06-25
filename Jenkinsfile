pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                sh "mvn -B -DskipTests clean package"
            }
        }

        stage("Test") {
            steps {
                sh "mvn test"
            }

            post {
                success {
                    echo "Tests passed"
                }

                failure {
                    echo "Tests failed"
                }
            }
        }
    }
}