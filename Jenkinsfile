pipeline {
    agent any

    environment {
        ImageRegistry = 'gabriel818'
        EC2_IP = '54.195.81.137'
        DockerComposeFile = 'docker-compose.yml'
        DotEnvFile = '.env'
    }

    stages {
        stage ("init"){
            steps { 
                script {
                    gv = load "scrip.groovy"
                }
            }
        }

        stage("buildImage") {
            steps {
                script {
                    gv.buildImage()
                }
            }
        }

        stage("pushImage") {
            steps {
                script {
                    gv.pushImage()
                }
            }
        }

        stage("deployCompose") {
            steps {
                script {
                    gv.deployCompose()
                }
            }
        }
    }
}
        
