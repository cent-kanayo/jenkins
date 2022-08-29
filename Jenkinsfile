pipeline{
    agent any
    stages{
        stage("testing"){
            steps{
                echo "testing staget"
            }
        }
        stage("ruuning"){
            steps{
                echo "running"
                sh '''
                    sudo ssh -i /var/lib/jenkins/cent.pem -t -o StrictHostHostKeyChecking=no ubuntu@
                    cd /var/www
                    sudo rm -rf html
                    sudo mkdir html
                    sudo git init
                    sudo git remote add origin
                    sudo git pull origin master
                '''
            }
        }
    }
}