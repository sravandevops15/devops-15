pipeline{
    agent any
    parameters {
        string(name:'DEPLOY_ENV',defaultValue: 'staging', description: 'Select the envinorments')
        booleanParam(name: 'DEBUG_BUILD', defaultValue: true, description: '') 
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
        
    }
    stages{
    stage('parameters'){
        steps{
            echo "${params.DEPLOY_ENV}"
            echo "${params.DEBUG_BUILD}"
            echo "${params.CHOICES}"
            
        }
    }
}
    
}
