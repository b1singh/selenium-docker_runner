pipeline{

    agent any
    parameters {
        choice choices: ['chrome', 'firefox'], description: 'select the browser', name: 'Browser'
    }


    stages{

        stage('Start Grid'){
            steps{
                bat "docker-compose -f grid.yaml up -d"
            }
        }

        stage('Run Test'){
            steps{
                bat "docker-compose -f test-suite.yaml up --pull=always"
            }
        }

    }
}