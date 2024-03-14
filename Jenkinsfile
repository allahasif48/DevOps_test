pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'asif48/flask-app' // Change this to your Docker Hub username and image name 
        SSH_KEY = credentials('admin') // Jenkins credential ID for SSH private key mm
        REMOTE_HOST = '18.224.70.151' // IP address or hostname of your EC2 instance
        REMOTE_USER = 'ec2-user' // Username to SSH into your EC2 instance
    }

       stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(env.DOCKER_IMAGE, '-f Dockerfile .')
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockercreds') {
                        docker.image(env.DOCKER_IMAGE).push()
                    }
                }
            }
        }

       
    }
}
