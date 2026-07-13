pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            steps {
                bat 'dotnet restore SoftUniBazar.sln'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build SoftUniBazar.sln --configuration Release --no-restore'
            }
        }

        stage('Unit Tests') {
            steps {
                bat 'dotnet test SoftUniBazar.Tests/SoftUniBazar.Tests.csproj --configuration Release --no-build'
            }
        }

        stage('Integration Tests') {
            steps {
                bat 'dotnet test SoftUniBazar.IntegrationTests/SoftUniBazar.IntegrationTests.csproj --configuration Release --no-build'
            }
        }
    }
}