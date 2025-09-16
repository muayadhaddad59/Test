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
        mail to: 'team@example.com',
             subject: "Build Success in Jenkins: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
             body: "Thank you"
    }
    failure {
        mail to: 'team@example.com',
             subject: "Build failed in Jenkins: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
             body: "Check the logs at ${env.BUILD_URL}"
    }
    }
}