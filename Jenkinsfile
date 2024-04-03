pipeline {
  agent any
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/ksaidoun/maven-samples-A6.git', branch: 'master')
      }
    }

    stage('verify') {
      steps {
        sh 'mvn verify'
      }
    }

    stage('clean') {
      steps {
        sh 'mvn clean'
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

  }
  tools {
    maven 'DHT_MVN'
    jdk 'DHT_SENSE'
  }
}