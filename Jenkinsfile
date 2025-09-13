pipeline{
    agent any
    stages{
        stage("Checkout"){
            steps{
                echo "========executing A========"
                checkout scm
            }
        }

        stage("Install"){
            steps{
                echo "INstalling dependanceies..."
                sh 'npm install'
            }
        }

        stage("Build"){
            steps{
                echo "Building the project.."
                // Here you cann add build steps if needed
            }
        }

        stage("Run Hello world"){
            steps{
                echo "Running Hello World app.."
                sh 'node index.js'
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}