pipeline {
    agent any

    stages {
        stage('W/O docker') {
            steps {
                sh '''
                    echo "without"
                    ls -la
                    touch No=container.txt
                '''

                
            }
        }
        stage('With') {
            agent {
                    docker {
                        image 'node:18-alpine'
                        reuseNode true
                    }
            }
            steps {
                sh '''
                     echo "with docker"
                     ls -la
                     touch Yes-Container.txt
                      
                   '''
            }
        }        
    }
}
