pipeline{
    agent any
    stages{
        stage('Dev'){
            parallel {
                stage('ONE'){
                steps{
                    catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                        exit 1
                        echo 'Stage One'
                    }
                    }
                post{
                    always{
                        echo 'Dev Stage one failed building parellel job2'
                        build 'Parallel-job-2'
                    }
                }
                  
                }
                stage('TWO'){
                steps{
                        echo 'stage two'
                    }
                    
                }
                stage('THREE'){
                steps{
                        echo 'stage three'
                    }
                    
                }
            }
        }
        stage('QA'){
            parallel {
                stage('ONE'){
                steps{
                    catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                        exit 1
                        echo 'Stage One'
                    }
                    }
                  
                }
                stage('TWO'){
                steps{
                        echo 'stage two'
                    }
                    
                }
                stage('THREE'){
                steps{
                        echo 'stage three'
                    }
                    
                }
            }
        }
        stage('PROD'){
            parallel {
                stage('ONE'){
                steps{
                    catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                        exit 1
                        echo 'Stage One'
                    }
                    }
                  
                }
                stage('TWO'){
                steps{
                        echo 'stage two'
                    }
                    
                }
                stage('THREE'){
                steps{
                        echo 'stage three'
                    }
                    
                }
            }
        }
    }
    post{
        always{
            echo 'Post step running after all stages !!!'
            sh 'ls -al'
        }
    }
}