pipeline {
  agent {

    node {
      label 'jenkins-node'
    }

    environment {
      TF_VAR_aws_secret_key = credentials('aws_secret_key')
      TF_VAR_aws_access_key = credentials('aws_access_key')
    }

  }
    stages {
        stage ('git') {
            steps {
                git 'https://github.com/ag4544/final-task.git'
            }
        }
        stage ('Initialize terraform') {
            steps {
                sh 'terraform init'
            }
        }
        stage ('Terraform apply') {
            steps {
              sh 'terraform apply -auto-approve'
            }
        }

    }
}
