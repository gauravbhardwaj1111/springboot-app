pipeline{
    agent any
    environment{
        IMAGE_NAME = 'yourdockerhubusername/demo-app'

    }
    tools{
        maven 'Maven 3.8.4'
        jdk 'JDK 17'
    }
    stages{
        stage('Checkout Code'){
            steps{
                git 'https://github.com/gauravbhardwaj1111/springboot-app.git'
            }

        }
        stage('Build with Maven'){
            steps{
                sh 'mvn clean package'
            }

        }
        stage('Build Docker Image'){
            steps{
                sh "docker build -t ${IMAGE_NAME} ." 
            }

        }
        stage('Deploy'){
            steps{
                echo "You can add deployment to EC2 or K8S here"
            }
        }
    }
    post{
        always{
            cleanWs()
        }
    }
}