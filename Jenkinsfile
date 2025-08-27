pipeline {
  agent any
  tools{
    maven 'maven 3.9.11'
  }
  
  stages{
      stage("build"){
          steps{
              echo 'Building...'
              sh 'mvn compile'
          }
      }
      stage("test"){
          steps{
              echo 'Testing...'
              sh 'mvn clean test'
          }
      }
      stage("package"){
          steps{
              echo 'Packaging...'
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
