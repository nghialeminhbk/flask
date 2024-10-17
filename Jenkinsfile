pipeline{
    agent any 
    stages{
        stage("Docker build"){
            steps{
                sh "docker build -t leminhnghiaitbk/flask-app ."
            }
        }

        stage("Docker push image") {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
                    sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
                    sh 'docker push ${env.dockerHubUser}flask-app:latest'
                }
            }
        }
    }
    post{
        success{
            echo "successfully"
        }
        failure{
            echo "failed"
        }
    }
}
