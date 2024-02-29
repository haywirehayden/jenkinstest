pipeline {
    agent any
    stages{
        stage("Cleanup"){
            steps{
                echo "Building"
                sh "docker rm -f \$(docker ps -aq) || true"
                sh "docker rmi -f \$(docker images) || true"
                sh "docker images"
                sh "docker ps"
            }
        }
        stage ("Build"){
            steps{
                sh "pwd"
                sh "ls"
                sh "docker build -t cjfitzy89/task1 . || true"
            }
        }
        stage ("Run Container"){
            steps{
                sh "docker run -d -p 80:5500 --name test cjfitzy89/task1 || true"
            }
        }
    }
}
