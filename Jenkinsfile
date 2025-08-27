pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'Building...'
        sh 'mvn compile'
      }
    }

    stage('test') {
      steps {
        echo 'Testing...'
        sh 'mvn clean test'
      }
    }

    stage('package') {
      steps {
        echo 'Packaging...'
        sh 'mvn package -DskipTests'
        archiveArtifacts '**/target/*.jar'
      }
    }

  }
  tools {
    maven 'Maven 3.9.11'
  }
  post {
    always {
      echo 'This pipeline is completed..'
    }

  }
}