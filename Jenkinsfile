pipeline {
//     environment {
//         aws_credential = "PuneetAWS"
//         bucket = "my-jenkinsanglar"
//         region = "ap-northeast-1"
//         webHook_url = "myWebHookURL"
//         TAG_NAME = "README.md"      
//     }
//   tools {
//     nodejs 'Node16'
//   }
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

        // stage('Upload to AWS') {
        //       steps {
        //           withAWS(region:'ap-northeast-1',credentials:'PuneetAWS') {
        //           bat 'echo "Uploading content with AWS creds"'
        //               s3Upload(file:'README.md', bucket:'my-jenkinsanglar')
        //           }
        //       }
        //  }

        stage("Upload"){
            steps{
                 bat 'echo "hello KB">hello.txt'
                //  bat 'type hello.txt'
                 withAWS(region:'ap-northeast-1',credentials:'PuneetAWS') {
                    
                    // bat 'echo "hello KB">hello.txt'
                    s3Upload (entries: [
                        [bucket: 'my-jenkinsanglar', sourceFile: "hello.txt"]
                    ])
                    // s3Upload(profileName: 'PuneetAWS', 
                    // userMetadata: [],
                    // dontWaitForConcurrentBuildCompletion: true,
                    // consoleLogLevel: 'INFO',
                    // pluginFailureResultConstraint: '',
                    // dontSetBuildResultOnFailure: true,
                    // entries: [[file:'hello.txt', bucket:'my-jenkinsanglar', path:'/']]
                    // )
                    // s3Download bucket: 'kb-bucket', file: 'downloadedHello.txt', path: 'hello.txt'
                    // bat 'cat hello.txt'
                // }
            }
            // steps{
            //     withAWS(region:"${region}", credentials:"${aws_credential}) {s3Upload(file:"${TAG_NAME}", bucket:"${bucket}", path:"/")
            //     }    
            }
        
        }
    }
}
