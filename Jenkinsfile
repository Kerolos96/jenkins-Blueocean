pipeline {
  agent any
  stages {
    stage('Check Java Version') {
      steps {
        sh 'java -version'
        sh 'javac -version'
      }
    }

    stage('Echo Version') {
      steps {
        sh 'echo print Maven Version'
        sh 'mvn -version'
      }
    }

    stage('Build JAR') {
      steps {
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/hello-demo-*.jar'
      }
    }

    stage('Unit Test Cases') {
      steps {
        sh 'mvn test'
      }
    }

  }
  tools {
    maven 'M399'
  }
}