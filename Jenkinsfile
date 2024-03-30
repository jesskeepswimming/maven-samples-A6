pipeline {
  agent any
  tools { 
      maven 'DHT_MVN' 
      jdk 'DHT_SENSE' 
  }
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/jesskeepswimming/maven-samples', branch: 'master')
      }
    }

    stage('clean') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

  }
}
