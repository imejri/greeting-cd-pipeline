pipeline {
    agent { label 'nodejs' }
    stages{
        stage('Test'){
            steps { 
                sh "node test.js"
            }
        }
        
        stage('Deploy') {
            steps {
                sh '''
                oc start-build greeting-metrics \
                --follow --wait -n metrics
                ''' 
            }
        }
    }
}
