pipeline {
  agent any
  tools { 
      maven 'DHT_MVN' 
      jdk 'DHT_SENSE' 
  }
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/jesskeepswimming/maven-samples-A6', branch: 'master')
      }
    }

    stage('git bisect') {
      steps {
        sh 'git bisect start 198644632661c67b6c32f59e9047c11a70685e15 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5'
      }
    }

    stage('bisect test') {
      steps {
        sh 'git bisect run mvn clean test'
      }
    }

  }
}
