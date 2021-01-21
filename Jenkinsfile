pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('Junit-test') {
      steps {
        junit '**/surefire-reports/**/*.xml'
      }
    }

    stage('Print-stage') {
      steps {
        sh 'echo $NAME'
      }
    }

  }
  environment {
    NAME = 'SAMPLE'
  }
}