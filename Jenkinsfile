def stagename = ""
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('maven-Build'){
            steps{
                echo 'Maven BUILD'
                script{
                    stagename = "maven-Build"
                }
            }
            post{
                aborted{
            emailext attachLog: true, body: 'Devops15 Report of this job $BUILD_NUMBER Failure occure Stage Name:${StageName}', compressLog: true, subject: 'Jenkins options testing :$JOB_NAME BuildNumber: $BUILD_NUMBER', to: 'sravanbunty.mj@gmail.com'
             }
            }
        }
        stage("Email Notification"){
            steps{
                echo 'enail.notification'
                sh 'sleep 60s'
                script{
                    stagename = "Email Notification"
                }
                
            }
            post{
                aborted{
            emailext attachLog: true, body: 'Devops15 Report of this job $BUILD_NUMBER  Failure occure Stage Name:$stagename', compressLog: true, subject: 'Jenkins options testing :$JOB_NAME BuildNumber: $BUILD_NUMBER StageName:${stagename}', to: 'sravanbunty.mj@gmail.com'
              }
            }
          
            
        }
    }
    post{
        fixed{
            emailext attachLog: true, body: 'Devops15 Report of this job $BUILD_NUMBER', compressLog: true, subject: 'Jenkins options testing :$JOB_NAME BuildNumber: $BUILD_NUMBER', to: 'sravanbunty.mj@gmail.com'
        }
        aborted{
            emailext attachLog: true, body: 'Devops15 Report of this job $BUILD_NUMBER', compressLog: true, subject: 'Jenkins options testing :$JOB_NAME BuildNumber: $BUILD_NUMBER', to: 'sravanbunty.mj@gmail.com'
        }
        success{
            emailext attachLog: true, body: 'Devops15 Report of this job $BUILD_NUMBER', compressLog: true, subject: 'Jenkins options testing :$JOB_NAME BuildNumber: $BUILD_NUMBER', to: 'sravanbunty.mj@gmail.com'
        }
    }
}
