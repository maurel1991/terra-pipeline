pipeline {
    agent any
    stages {
        stage('Deploy to AWS') {
            steps {
                script {
                    withCredentials([[
                        $class: 'AmazonWebServicesCredentialsBinding',
                        credentialsId: 'aws-credentials'
                    ]]) 
                        sh '''
                        aws configure set aws_access_key_id $AWS_ACCESS_KEY_ID
                        aws configure set aws_secret_access_key $AWS_SECRET_ACCESS_KEY
                        '''
                    }
                }
            }

        stage('terraformValidate'){
            steps {
                sh 'terraform init'
                sh 'terraform validate'
            }
        }
            
    }
}

