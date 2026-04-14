pipeline {
 agent any

 tools {
  jdk 'jdk'
 }

 stages {
  stage('Checkout') {
   steps {
    git branch: 'main', url: 'https://github.com/RohanVSomani/MyGradleApp.git'
   }
  }

  stage('Build') {
   steps {
    sh 'chmod +x gradlew'
    sh './gradlew build'
   }
  }

  stage('Test') {
   steps {
    sh './gradlew test'
   }
  }

  stage('Run Application') {
   steps {
    sh './gradlew run'
   }
  }
 }

 post {
  success {
   echo 'Build and deployment successful!'
  }
  failure {
   echo 'Build failed!'
  }
 }
}
