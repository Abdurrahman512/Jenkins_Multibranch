pipeline{
    agent any
    stages{
        stage('Git Clone'){
            steps{
                git branch: 'main', url: 'https://github.com/Abdurrahman512/Jenkins_Multibranch.git'
            }
        }
        stage('Maven Build'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Create Docker image'){
            steps{
                sh 'rm -rf dockerimg'
                sh 'mkdir dockerimg'
                sh 'cd dockerimg'
                sh 'cp /var/lib/jenkins/workspace/test_class_multibranch_pipeline/target/maigolab_hello-1.0.0.jar  .'    
                sh 'docker build -t webimage:$BUILD_NUMBER .'
                sh 'sudo docker  run -itd --name webserver$BUILD_NUMBER -p 8081 webimage:$BUILD_NUMBER'
            }
        }
    }
}
