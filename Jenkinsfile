pipeline {
  agent any
  stages {
    stage('Deploy application') {
      steps {
        sh '''git clone https://github.com/mikbuch/chartjs-real-time-example.git
cd chartjs-real-time-example
git pull'''
      }
    }

  }
}