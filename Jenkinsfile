pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }

    stages {
        stage("Build") {
            steps {
                bat "mvn -B -DskipTests clean package"
            }
        }

        stage("Test") {
            steps {
                bat "mvn test"
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
