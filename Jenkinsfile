pipeline{
  agent any
  stages {
    stage('Clone repository') {
      steps {
        checkout([$class: 'GitSCM',
                  branches: [[name: '*/main']],
                  userRemoteConfigs: [[url: 'https://github.com/NidhiPandukalGururaj/PES1UG21CS380_Jenkins.git']]])
      }
    }
    stage('Build') {
      steps{
        build 'PES1UG21CS380-1'
        sh 'g++ prg1.cpp -o output'
      }
    }
    stage('Test') {
      steps {
        sh './output'
      }
    }
    stage('Deploy') {
      steps{
        echo 'deploy'
      }
    }
  }
  post {
    failure{
      error 'Pipeline failed'
    }
  }
  
        
    
