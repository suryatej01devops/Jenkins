pipeline {
    agent {
        node{
            label 'Agent-1'
        }
    }          // where to run the pipeline (any agent/node)
    stages {

        stage('Build') {
            steps {
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

    
}