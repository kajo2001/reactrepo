pipeline{
    agent any
    tools {
        nodejs "NodeJs"
    
    }

    stages {
        stage("Checkout"){
            steps {
                checkout scm
            }
        }

        stage("Install Dependencies"){
            steps {
                bat "npm install"
            }
        }

        stage("Test") {
            steps {
                echo "Building the application"
               // bat "npm test"
            }
        }

        stage ("Build") {
            steps {
                bat "npm run build"
            }
        }

        stage ("Deployment") {
            bat "del /q /s C:\\inetpub\\wwwroot\\react\\*"
            bat "xcopy /E /I /Y build\\* C\\inetpub\\wwwroot\\react"    
               }
    }
}