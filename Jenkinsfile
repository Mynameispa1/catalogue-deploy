pipeline {
    agent {
    node {
        label 'Agent-1'
        }
    }

    //   environment { 
    //     packageVersion = ''
    //     nexusURL = '172.31.84.200:8081'
    // }

     options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()       //to run only one build at a time
    }

    parameters {
        string(name: 'version', defaultValue: '1.2.0', description: 'What is the artifacts version')
        string(name: 'environment', defaultValue: 'dev', description: 'What is the environment')

        // text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        // booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        // choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        // password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
  // Build stage
     stages {
        stage('Print version') {
            steps {
                sh """
                   echo "version is: ${params.version}"
                   echo "environment is: ${params.environment}"
                """
            }
        }

    //post build
    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }

        failure { 
            echo 'This is Failed...!'
        }

        success {
            echo 'This is success...!'
        }
    }
}     
