pipeline {
 agent any
 tools {
 maven 'Maven3'
 jdk 'Java17'
 }
 stages {
 stage('Checkout') {
 steps {
 git branch: 'main',
 url: 'https://github.com/AkshyaAbishek/Java-Sample.git'
 }
 }
 stage('Build') {
 steps {
  dir('java-ci-pipeline'){
 bat 'mvn clean compile'
  }
 }
 }
 stage('Test') {
 steps {
  dir('java-ci-pipeline'){
 bat 'mvn test'
 }
 }
 post {
 always {
 junit 'java-ci-pipeline/target/surefire-reports/*.xml'
 }
 }
 }
 stage('Package') {
 steps {
  dir('java-ci-pipeline'){
 bat 'mvn package'
 }
 }
 }
 post {
 success {
 echo '■ Build Successful!'
 }
 failure {
 echo '■ Build Failed!'
 }
 }
}



