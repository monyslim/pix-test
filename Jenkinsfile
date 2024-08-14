pipeline{
    agent any
    stages{
        stage("test"){
            steps{
                sh '''
                        echo "welcome to test"
                   '''
            }
        }
        stage("build"){
            steps{
                sh '''
                        ## get the project
                        cd /home/cyclobold-computer-3/pix-mix
                        docker build -t monyslim/test-pixmix:1 .
                        docker run -d --name runner -p 802:80 monyslim/test-pixmix:1
                        docker stop runner
                        sleep 300
                        docker rm runner
                        echo '-------------done------------'
               '''
            }
        }
    }   
}