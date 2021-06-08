pipeline {
  agent any

  tools {
    maven 'Maven 3.6.3'  // this name is what you added earlier to the jenkins
  }

  stages{
      stage("build"){
          steps{
              echo 'compiling sysfoo app'
              sh 'mvn compile'    // sh means run a shell command. The shell command can be generated in jen 
          }
      }
      stage("test"){
          steps{
              echo 'running unit tests'
              sh 'mvn clean test'
          }
      }
      stage("package"){
          steps{
              echo 'packaging app into a war file'
              sh 'mvn package -DskipTests'
          }
      }
  }

  post{
    always{
        echo 'This pipeline is completed..'
    }
  }
}