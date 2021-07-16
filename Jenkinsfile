pipeline {
    agent { label 'ubuntu' }
    stages {
        stage ('start mule') {
            steps {
                sh '../../muleRuntime/mule-enterprise-standalone-4.3.0-20210119/bin/mule start'
            }
        }
    
    }
}
