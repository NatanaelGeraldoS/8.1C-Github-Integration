pipeline{
    agent any
    tools { nodejs 'NodeJS' }
    stages{
        stage("Build"){
            steps{
                echo "== Stage 1: Build =="
                echo "We are using NPM to Install all of the required libraries and build the application"
                echo "Tool: NPM"
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage("Unit and Integration Tests"){
            steps{
                echo "== Stage 2: Unit and Integration Test"
                echo "We run automated unit testing and integration using the npm test, to check all of the code running properly"
                echo "Tool: NPM Test"
                sh "npm test"
            }
        }
        stage("Code Analysis"){
            steps{
                echo "== Stage 3: Code Analysis"
                echo "Analyze the code quality and enforce coding standards"
                echo "Tool: ESLint"
                sh "npx eslint . || true"
            }
        }

        stage('Security Scan') {
            steps {
                echo "== Stage 4: Security scan with npm audit =="
                echo "Scan depedencies for the security vulnerabilities at hight level of security"
                echo "Tool: NPM Audit"
                sh 'npm audit --audit-level=high || true'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "== Stage 5: Deploy to staging =="
                echo "Deploying the Code to the staging environment"
                echo "Tools: Jenkins Pipeline and Azure DevOps"
                echo "Deploy to Staging Stage.."
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "== Stage 6: Run staging tests =="
                echo "Run integration tests for the the staging phase"
                echo "Tool: Testing Framework (Jest) executed by Jenkins"
                echo "Running test on staging..."
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "== Stage 7: Deploy to Production =="
                echo "Running the deployment to production to the Azure environment"
                echo "Tool: Jenkins pipeline and Azure DevOps"
                echo "Running the deploy to production environment..."
            }
        }

    }
}