pipeline {
    agent any

    stages {
        stage('Checkout') { // Capitalize stage name for consistency
            steps {
                git branch: 'main',
                    url: 'https://github.com/ash2code/java_source.git'
            }
        }

        stage('Code Build') { // Capitalize stage name
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp /var/lib/jenkins/workspace/${JOB_NAME}/target/*.war /usr/share/tomcat9/webapps/' // Copy only WAR file
            }
        }
    }

    post {
        success {
            echo "Deployment successful"
        }
        failure {
            echo "Deployment failed" // Correct spelling of "failed"
        }
    }
}
