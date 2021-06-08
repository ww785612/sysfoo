pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'compiling sysfoo app'
        sh '''

mvn compile
echo "shell script hello"'''
      }
    }

    stage('test') {
      steps {
        echo 'running unit tests'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'packaging app into a war file'
        sh 'mvn package -DskipTests'
      }
    }

  }
  tools {
    maven 'Maven 3.6.3'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
}