pipeline {
    agent any
    stages {
        stage('Gathering') {
            steps {
                echo 'Gathering APIs'
                git url: 'https://github.com/andresescobarcotan/APISwagger.git'
                script {
                  sh ''' 
                     DIR_1="workspace/"
                     DIR_2="files/"
                     if [ ! -d "$DIR_1" ]; then
                        mkdir workspace
                     fi
                     if [ ! -d "$DIR_2" ]; then
                        mkdir files
                     fi
                     mv *.json files/
                     ls files/
                     cat files/bookflix.json
                     '''
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
                git url 'https://github.com/andresescobarcotan/APISwagger.git'
                    branch draft
                sh '''
                    git add files/bookflix.json
                    git commit -m 'Bookflix into draft'
                    git push origin draft
                '''
            }
            }
        }
    }
}
