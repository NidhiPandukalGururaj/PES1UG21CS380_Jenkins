pipeline {
    agent any 
    stages {
        stage('Clone repostiory'){
            steps {
                checkout([$class:'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/NidhiPandukalGururaj/PES1UG21CS380_Jenkins.git']]])
            }
        }
        stage('Build') { 
            steps {
                echO "This is Build stage."
                build 'PES1UG21CS380-1'
                sh 'g++ prg1.cpp -o output'
                echo "Build Stage Successful"
            }
        }
        stage('Test') { 
            steps {
                echo "This is Test stage." 
                sh './output'
                echo "Test Stage Successful"
            }
        }
        stage('Deploy') { 
            steps {
                echo "This is Deploy stage."
                echo "Deployment Success"
            }
        }
    }
    post{
        failure{
            error 'Pipeline Failed'
        }
    }
}
