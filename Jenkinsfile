pipeline {
    agent {
        label 'AGENT-1'
    }
    environment {
        appVersion = ''
    }
    options {
        timeout(time:30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    // parameters {
    //     string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
    //     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
    //     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password') 
    // }
    // Build
    stages {
        stage('Read Package.json Version') {
            steps {
                script {
                    // Read the package.json file
                    def packageJson = readJSON file: 'package.json'

                    // Access a specific field, e.g., 'version'
                    appVersion = packageJson.version

                    // Print the version
                    echo "Package version: ${version}"
                }
            }
        }
        stage('Test') {
            steps {
                script{
                    echo 'Testing..'
                }
            }
        }
        
    }

    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        success { 
            echo 'Hello Success'
        }
        failure { 
            echo 'Hello Failure'
        }
    }
}


