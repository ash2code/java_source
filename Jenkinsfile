pipeline {
    agent any 
    stages {
        stage ("checkout") {
            steps {
                git branch: 'main', 
                url: 'https://github.com/ash2code/java_source.git'
            }
        }
        stage ("code-build") {
            steps {
                sh "mvn clean package"
            }
        }
    }
}
