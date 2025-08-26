pipeline{
    agent any
    tools { maven 'NodeJS' }
    stages{
        stage("Build"){
            steps{
                sh 'npm install'
                sh 'npm run build'
            }
        }
    }
}