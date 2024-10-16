pipeline{
    agent any
    stages{
        stage("build"){
            steps{
                echo "====++++Build something++++===="
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}