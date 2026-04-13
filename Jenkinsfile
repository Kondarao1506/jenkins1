pipeline{
    agent{
        label 'AGENT-1'
    }
    stages{
        stage('Build Image'){
            steps{
                sh """
                docker build -t kondarao/hello:v1 .
                """
            }
        }

        stage('Run image'){
            steps{
                sh """
                docker rm -f kondarao/hello:v1
                docker run -d -p 80:80 kondarao/hello:v1

                """
            }
        }
    }

    post{

        always{
            cleanWs()
        }
        failure{
            echo "build and run failed"
        }
    }
}