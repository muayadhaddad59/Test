pipeline{
    agent any 

    stages{
        stage("Check out"){
            steps{
                echo "==== Ececuting A======"
                checkout scm
            }
        }

        stage("Install"){
            steps{
                echo "INstalling dependancies"
                sh 'npm install'
            }
        }

        stage("Build"){
            steps{
                echo "Building the project"
            }
        }

        stage("Run Hello World"){
            steps{
                echo "Running Hello world App"
                sh "node index.js"
            }
        }
    }
}