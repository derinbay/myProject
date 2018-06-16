pipeline {
  agent { label 'slave' }
  tools {
    maven 'maven_3.5.3'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/derinbay/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
