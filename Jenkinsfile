pipeline {
    agent any
    stages {
        stage ('git checkout'){
            steps {
            echo ("Check out the code from the defined GITHub repo")
            }
        }
        stage ("Build the Docker Image"){
            steps {
            echo "Starting to the build the docker image as defined in the Docker File"
            sh "docker build -t pipe-line-image:latest ."
            }
        }    
	stage ("Build the Docker Container from the Docker Image"){
            steps {
            echo "Starting to the build the docker container from the Docker image"
            sh "docker run -d --name first-container-via-pipeline -p 80:80 pipe-line-image:latest"
	    }
	}
        stage ("Push to Docker Hub"){
            steps {
            echo "Pushing to the docker image to the docker hub"
            }
        }    
    }   
}