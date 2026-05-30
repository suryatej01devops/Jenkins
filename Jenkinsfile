pipeline {
    agent {
        node{
            label 'Agent-1'
        }
    }          // where to run the pipeline (any agent/node)

    environment{
        NAME = "surya"
    }
    options {
        timeout(time: 10, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    stages {

        stage('Build') {
            steps {
                script{
                    echo "${NAME}"
                    echo "i am the script to hello"
                    sleep 5
                }
                echo 'Building...'
                // sh 'mvn clean package'  or  sh 'npm install'
                
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // sh 'mvn test'  or  sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            
            }
        }
    }
    post{
        always{
        echo "i will always say hello again"
        cleanWs()
        }
        success {
            echo "i will run if success"
        }
        failure{
            echo "i will run if failire"
        }

    }
    
}