pipeline{
    agent any    
    stages {
        stage("sonar quality check"){
            agent {
                docker {
                    image 'jdk8-jammy'
                }
            }
            steps {
                script {
                    withSonarQubeEnv(credentialsId: 'sonar-token') {

                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
    
                    }
                }               
            
            }
        }
    }
}

        