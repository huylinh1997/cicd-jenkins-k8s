pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token2') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                    }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
                } 
            }
        }

    }
}