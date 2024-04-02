pipeline {
  agent any
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/ksaidoun/maven-samples-A6.git', branch: 'master')
      }
    }

    stage('run') {
      steps {
        sh '''git checkout 198644632661c67b6c32f59e9047c11a70685e15
mvn clean test
git checkout 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5
mvn clean test
git checkout master
git bisect start
git bisect good 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5
git bisect bad 198644632661c67b6c32f59e9047c11a70685e15
git checkout 8bad1c6db9cf6930abd8e52ff5dfdd046194ae9b
mvn clean test
git bisect bad 8bad1c6db9cf6930abd8e52ff5dfdd046194ae9b
git checkout 26438de182f7a00147b5e53e9408a3c3745ca509
mvn clean test
git bisect bad 26438de182f7a00147b5e53e9408a3c3745ca509
git checkout 34d31973a0cc1f3d77cd5038fc9c01eeba7ec183
mvn clean test'''
      }
    }

  }
  tools {
    maven 'DHT_MVN'
    jdk 'DHT_SENSE'
  }
}