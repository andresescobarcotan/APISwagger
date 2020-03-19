node {
    stage('Gathering') {
        echo 'Gathering APIs'
        checkout scm
        def browsers = ['chrome', 'firefox']
        for (int i = 0; i < browsers.size(); ++i) {
            echo "Testing the ${browsers[i]} browser"
        }
    }
    
    stage('Checking APIs updates') {
        echo 'Checking if there are any updates within the API definition files'
    }
    
    stage('Transformation into Markdown') {
        echo 'Calling docker image to transform the APIs into Markdown'
    }
}