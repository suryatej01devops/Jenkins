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
    parameters {
        string(name: 'Surya teja chatla', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'Devops engineer ', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {

        stage('Build') {
            steps {
                script{
                    echo "${NAME}"
                    echo "i am the script to hello"
                }
                echo 'Building...'
                // sh 'mvn clean package'  or  sh 'npm install'
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
                
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // sh 'mvn test'  or  sh 'npm test'
            }
        }

        stage('Deploy') {
            input {
            message "Should we continue?"
            ok "Yes, we should."
            submitter "alice,bob"
            parameters {
                string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
            }
            }
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
