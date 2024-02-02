pipeline {
   agent any
   options {
    timeout(time: 20, unit: 'MINUTES')
   }
   stages {
    stage('Pull Npm Dependencies'){
        steps {
            sh 'npm install'
        }
    }
    stage('Build Docker Image') {
        steps {
            script {
                docker.build("748527796092.dkr.ecr.eu-west-1.amazonaws.com/netflix-react:latest")
            }
        }
    }
    stage('Trivy Scan Image'){
        steps {
            sh 'trivy image --format template --output trivy_report.html 748527796092.dkr.ecr.eu-west-1.amazonaws.com/netflix-react:latest'
        }
    }
    stage('Push to ECR'){
        steps {
            script {
                //https://<AwsAccountNumber>.dkr.ecr.<region>.amazonaws.com/netflix-app', 'ecr:<region>:<credentialsId>
                docker.withRegistery('https://748527796092.dkr.ecr.eu-west-1.amazonaws.com/netflix-react', 'ecr:eu-west-1:Mitchel-AWS-Credentials'){
                    // build image
                    def myImage = docker.build("748527796092.dkr.ecr.eu-west-1.amazonaws.com/netflix-react:latest")
                    // push image
                    myImage.push()
                }
            }
        }
    }
  }
}
