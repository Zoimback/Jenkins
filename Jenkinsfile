pipeline {
    agent any

    environment {
        GITHUB_CREDENTIALS = credentials('github-pat')
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    def gitUrl = 'https://github.com/Zoimback/Jenkins.git'
                    def gitCredentialsId = env.GITHUB_CREDENTIALS

                    // Using the credentials to clone the repository
                    checkout([$class: 'GitSCM', 
                        branches: [[name: '*/main']], 
                        doGenerateSubmoduleConfigurations: false, 
                        extensions: [], 
                        userRemoteConfigs: [[
                            url: gitUrl,
                            credentialsId: gitCredentialsId
                        ]]
                    ])
                }
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building...'
                // Add your build steps here
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                // Add your test steps here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deploy steps here
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
