pipeline {
  agent any
  stages {
    stage('Echo Version') {
      steps {
        sh 'echo Print Maven Version'
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/kk-jenkins-mvn-sb-hello-world*.jar'
      }
    }

    stage('Unit Test') {
      steps {
        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/TEST-*.xml', keepTestNames: true, keepProperties: true)
      }
    }

  }
  tools {
    maven 'M3911'
    jdk 'JDK24'
  }
}