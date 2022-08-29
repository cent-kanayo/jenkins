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
                    sudo ssh -i /var/lib/jenkins/cent.pem -t -o StrictHostKeyChecking=no ubuntu@ec2-52-90-52-191.compute-1.amazonaws.com
                    cd /var/www
                    sudo rm -rf html
                    sudo mkdir html
                    cd html
                    sudo git init
                    sudo git remote add origin https://github.com/cent-kanayo/jenkins.git
                    sudo git pull origin master
                '''
            }
        }
    }
}