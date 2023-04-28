pipeline {
    agent any
    stages {
    stage('SonarQube') {
  steps {
    withSonarQubeEnv('SonarQube Server') {
      sh 'mvn clean package sonar:sonar'
    }
  }
}
