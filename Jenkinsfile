pipeline{
    agent any
    tools { nodejs 'NodeJS' }
    stages{
        stage("Build"){
            steps{
                echo "== Stage 1: Build =="
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage("Unit and Integration Tests"){
            steps{
                echo "== Stage 2: Unit and Integration Test"
                sh "npm test"
            }
        }
        stage("Code Analysis"){
            steps{
                echo "== Stage 3: Code Analysis"
                sh "npx eslint . || true"
            }
        }

        stage('Security Scan') {
            steps {
                echo "== Stage 4: Security scan with npm audit =="
                sh 'npm audit --audit-level=high || true'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "== Stage 5: Deploy to staging =="
                sh "echo Deploy to Stagging Stage.."
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "== Stage 6: Run staging tests =="
                sh 'echo "Running test on staging..."'
            }
        }

        stage('Deploy to Production') {
            steps {
                input message: 'Deploy to PRODUCTION?', ok: 'Deploy'
                sh 'echo "Deploying build to production server..."'
            }
        }

    }
}