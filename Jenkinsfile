pipeline{
    agent any

    stages{
        stage("pull"){
            steps{
                git branch:'main',url:'https://github.com/amansah23/flask-jenkins'
            }
        }
        stage('image'){
            steps{
                sh 'docker build -t myflask .'
            }
        }
        stage('run'){
            steps{
                sh 'docker run -dit --name flaskcontainer myflask'
            }
        }
    }
    post{
        sucess{
            echo "run successfully"
        }
        failure{
            echo "Pipeline Failed! Check Logs..."
        }
    }

}