pipeline{
    agent any    
    stages {
        stage("sonar quality check"){
            agent {
                docker {
                    image 'gradle'
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

        