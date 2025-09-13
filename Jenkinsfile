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
 sh 'mvn clean compile'
 }
 }
 stage('Test') {
 steps {
 sh 'mvn test'
 }
 post {
 always {
 junit '**/target/surefire-reports/*.xml'
 }
 }
 }
 stage('Package') {
 steps {
 sh 'mvn package'
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

