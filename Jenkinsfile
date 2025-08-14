pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3911"
        jdk 'JDK24'
    }

    stages {
        stage('Echo Version') {
            steps {
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }

        stage('Build') {
            steps {
                // Get some code from Github repository
                // git branch: 'main', url: 'https://github.com/bala-testmails/jenkins-mvn-spring-boot-hello-world.git'

                // Run Maven Package CMD
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
