pipeline{
    agent any
    stages{
        stage('Git Clone'){
            steps{
                git branch: 'test', url: 'https://github.com/Abdurrahman512/Jenkins_Multibranch.git'
            }
        }
        stage('Maven Test'){
            steps{
                sh 'mvn test'
            }
        }
    }
}
