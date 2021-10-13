pipeline {
    environment {
        aws_credential = "PuneetAWS"
        bucket = "my-jenkinsanglar"
        region = "ap-northeast-1"
        webHook_url = "myWebHookURL"
        TAG_NAME = "README.md"      
    }
  tools {
    nodejs 'Node16'
  }
    agent any
    stages {
        stage('Check version') {
            steps {
                echo 'Cleaning..'
               
            }
        }
        // stage('Install dependencies') {
        //     steps {
        //         echo 'Install deps..'
        //         bat 'npm install'
        //     }
        // }
        // stage('Test') {
        //     steps {
        //         echo 'Testing..'
        //         bat 'npm test'
        //     }
        // }
        // stage('Package') {
        //     steps {
        //         echo 'npm build'
        //     }
        // }

        stage("Upload"){
            steps{
                withAWS(region:"${region}", credentials:"${aws_credential}) {
                    s3Upload(file:"${TAG_NAME}", bucket:"${bucket}", path:"/")
                }    
            }
        
        }
    }
}
