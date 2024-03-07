pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                echO "This is Build stage."
                build job 'PES1UG21CS380-1'
                sh 'g++ ./main/hello.cpp -o output'
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
