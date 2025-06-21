pipeline {
    environment {
        dockerimagename = "sarthakbanerjee/kubernetesnodejs"
        dockerimage = ""
    }
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Docker Build') {
            steps {
                script {
                    dockerimage = docker.build dockerimagename
                }
            }
        }
    }
}