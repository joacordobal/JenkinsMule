pipeline {
    agent { label 'ubuntu' }
    stages {
        stage ('start mule') {
            steps {
                sh '../../muleRuntime/mule-enterprise-standalone-4.3.0-20210119/bin/mule start'
            }
        }

        stage ('wait') {
            steps {
                 echo 'Waiting 5 minutes for deployment to complete prior starting smoke testing'
                sleep(time:3,unit:"SECONDS")
            }
        }
    
    }
}
