pipeline {
    agent any
    stages{
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t javatechie/devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   withCredentials([string(credentialsId: 'dockerpwd', variable: 'dockerpwd')]) {
                   sh 'docker login -u frimps -p ${dockerpwd}'

}
                   sh 'docker push javatechie/devops-integration'
                }
            }
        }
    }
}
