pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            when { branch 'main' }
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            when { branch 'main' }
            steps {
                sh 'dotnet build --no-restore --configuration Release'
            }
        }

        stage('Test') {
            when { branch 'main' }
            steps {
                sh 'dotnet test --no-build --verbosity normal --configuration Release'
            }
        }
    }
}
