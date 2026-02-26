pipeline{
    agent any
    
    environment {
                  APP_NAME = "spring-security-jwt"
                  DOCKER_IMAGE = "spring-security-jwt:latest"
    }

    stages {

        stage('Checkout Code') {
            steps {
                    git branch: 'main', url: 'git@github.com:gurkiran333/springboot-jwt-auth-devops.git'
            }
        }
    
        stage('Build Application') {
            steps {
                    sh '''
                    chmod +x mvnw
                    ./mvnw clean package -DskipTests
                    '''
            }
        }
    
        stage('Build Docker Image') {
            steps {
                    sh '''
                    docker build -t $DOCKER_IMAGE . 
                    '''
            }
        }
    
        stage('Run Docker Container') {
            steps {
                    sh '''
                    docker rm -f $APP_NAME || true
                    docker run --name $APP_NAME -d -p 8082:8080 $DOCKER_IMAGE
                    '''
            }
        }
    }

    post {
        success {
            echo "Build & Deployment Successful"
        }
        failure {
            echo "Pipeline Failed"
        }
    }   
}