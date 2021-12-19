pipeline{
    agent any
    environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        // stage("sonar quality check"){
        //     agent {
        //         docker {
        //             image 'openjdk:11'
        //         }
        //     }
        //     steps{
        //         script{
        //             withSonarQubeEnv(credentialsId: 'sonar-token2') {
        //                 sh 'chmod +x gradlew'
        //                 sh './gradlew sonarqube'
        //             }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
        //         } 
        //     }
        // }

        stage("docker build & docker push"){
            steps{
                script{
                    withCredentials([string(credentialsId: 'docker_pass', variable: 'docker_password')]) {
                             sh '''
                                docker build -t 34.80.182.49:8083/springapp:${VERSION} .
                                docker login -u admin -p $docker_password 34.80.182.49:8083 
                                docker push  34.80.182.49:8083/springapp:${VERSION}
                                docker rmi 34.80.182.49:8083/springapp:${VERSION}
                            '''
                    }
                }
            }
        }

    }
}