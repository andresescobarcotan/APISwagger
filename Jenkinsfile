pipeline {
    agent any
    stages {
        stage('Gathering') {
            steps {
                echo 'Gathering APIs'
                git url: 'https://github.com/andresescobarcotan/APISwagger.git'
                script {
                  sh 'dir *.json'
                }    
                
            }
        }
    
    
        stage('Checking APIs updates') {
            steps {
                echo 'Checking if there are any updates within the API definition files'
            }
        }
        
        stage('Transformation into Markdown') {
            steps {
                echo 'Calling docker image to transform the APIs into Markdown'
            }
        }
    }
}
