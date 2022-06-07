pipeline {
  agent { any { image 'ruby:2.6.1' } }
  stages {
    stage('requirements') {
      steps {
        sh 'bundler'
      }
    }
    stage('build') {
      steps {
        sh 'bundle install'
      }
    }
    stage('test') {
      steps {
        sh 'rake ci:all'
      }
      post {
        always {
          junit 'test/reports/TEST-AppTest.xml'
        }
      }    
    }
  }
}
