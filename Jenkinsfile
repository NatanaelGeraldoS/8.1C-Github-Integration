pipeline{
    agent any
    tools { maven 'Maven3' }
    stages{
        stage("Build"){
            steps{
                sh 'mvn -B -DskipTests clean package'
            }
        }

        stage('Unit & Integration Tests'){
            steps{
                sh 'mvn -B verify'
            }
        }
    }
}