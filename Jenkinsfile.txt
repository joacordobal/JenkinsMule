pipeline {
    agent { label 'ubuntu' }
    stages {


        stage ('stop muleruntime') {
            steps {
                sh '../../muleRuntime/mule-enterprise-standalone-4.3.0-20210119/bin/mule stop'
            }
        }

        stage ('wait') {
            steps {
                 echo 'Waiting 5 minutes for deployment to complete prior starting smoke testing'
                sleep(time:60,unit:"SECONDS")
            }
        }

        stage ('copy jar update') {
            steps {
                sh 'cp muleproject-tshirt2.jar ../../muleRuntime/mule-enterprise-standalone-4.3.0-20210119/apps/muleproject-tshirt2.jar'
            }
        }

        stage ('start mule') {
            steps {
                sh '../../muleRuntime/mule-enterprise-standalone-4.3.0-20210119/bin/mule start'
            }
        }
    
    }
}
