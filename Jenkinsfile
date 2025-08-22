pipeline {
    agent any
    tools {
        maven 'Maven3' // Ensure "Maven3" is defined in Jenkins > Global Tool Configuration
    }
    stages {
        stage('Build with Maven') {
            steps {
                withMaven(traceability: true) {
                    script {
                        if (isUnix()) {
                            sh 'mvn clean install'
                        } else {
                            bat 'mvn clean install'
                        }
                    }
                }
            }
        }
    }
    post {
        success {
            echo 'Build completed successfully.'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
