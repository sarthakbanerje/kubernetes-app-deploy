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

        // stage('Docker Build') {
        //     steps {
        //         script {
        //             //dockerimage = docker.build dockerimagename
        //             sh 'docker build -t ${dockerimagename}:${BUILD_NUMBER} .'
        //         }
        //     }
        // }
        stage ('Docker Build Push') {
            steps {
                scripts {
                    docker.withRegistry ('https://registry.hub.docker.com','dockerhubregistry') {
                        def customImage = docker.build("${dockerimagename}:${env.BUILD_ID}")
                        customImage.push()
                        }
                }
            }
        }
    }
}