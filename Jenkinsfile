pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'g++ prg1.cpp -o output'
                 build job: 'PES1UG21CS380-1', wait: false
                 echo 'Build  successful'
            }
        }

        stage('Test') {
            steps {
                sh './output'
                echo 'Test  successful'
            }
        }

        stage('Deploy') {
            steps {
               
                 echo 'Deploy 3 successful'
            }
        }
    }

    post {
        failure {
            
                error 'Pipeline Failed'
          
        }
    }
}
