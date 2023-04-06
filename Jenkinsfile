def countinueotherstages = false
pipeline{
    agent any
    stages{
        stage('build Name'){
            steps{
                script{
                    currentBuild.displayName = "${BUILD_NUMBER}-${JOB_NAME}-${BUILD_ID}"
                    currentBuild.description = "continue other stages if stage fails"
                    
                }
                 
            }
        }
        stage('stage1'){
            steps{
                script{
                    try{
                        sh "echo stage1"
                    } catch (Exception e){
                        countinueotherstages = true
                    }
                    if(countinueotherstages){
                        catchError(buildResult:'SUCCESS',stageResult:'FAILURE'){
                            sh "exit 1"
                        }
                    }
                }
            }
        }
        stage('stage2'){
            when {
                expression{
                    !countinueotherstages
                }
                
            }
            steps{
                sh "echo stage2"
            }
        }
        stage('stage3'){
            when{
                expression{
                    countinueotherstages
                }
            }
            steps{
                echo "stage3"
            }
        }
    }
}
