pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v $HOME/.m2:/root/.m2'
        }
    }
    stages {
        stage('Gathering') {
            steps {
                sh 'mvn -B'
                echo 'Gathering APIs'
                checkout scm
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
