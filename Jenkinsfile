pipeline{
    agent any
    stages{
        stage('CodeScan'){
            steps{
                sh 'trivy fs . -o file.txt'

            }
            
        }
        stage('terraform validate'){
            steps{
                sh 'terraform init'
                sh 'terraform validate'

            }
            
        }
    }
}