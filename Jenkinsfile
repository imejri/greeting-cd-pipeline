pipeline {
    agent { label 'nodejs' }
    stages{
        stage('Test'){
            steps {
                dir('greeting-cd-pipeline') {
                    sh "node test.js"
                }
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
