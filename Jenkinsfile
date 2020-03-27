pipeline {
    agent any
    stages {
        stage('Webhook Called'){
            steps {
	    	git url: 'https://github.com/andresescobarcotan/APISwagger.git',
			credentialsId: 'git-personal'
			
            echo 'I`ve been called through a webhook'   
            }
        }
    }
}
