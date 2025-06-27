pipeline {
    agent any


    stages {
        stage('Check Branch') {
            when {
                anyOf {
                    branch 'main'
                    branch pattern: 'feature/**'
                }
            }
        }

        stage('Restore') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
