```groovy
pipeline {

    agent any

    tools {
        maven 'Maven3'
        jdk 'JDK8'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/siddhi3022/p555.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }

            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
    }

    post {
        success {
            echo 'All tests passed successfully.'
        }

        failure {
            echo 'One or more tests failed.'
        }
    }
}
```
