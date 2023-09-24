pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                echo "pulling...."
                // Checkout code from GitHub
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/master']], 
                    userRemoteConfigs: [[
                        url: 'https://github.com/Tazarkour/devopstest.git',
                    ]]
                ])
            }
        }
        stage('Build Maven') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Date') {
            steps {
                // Display the current date and time
                sh 'date'
            }
        }
    }

}




