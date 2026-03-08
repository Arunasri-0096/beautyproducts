pipeline {
    agent any

    stages {

        stage('Git Checkout') {
            steps {
                git branch 'main', url: 'https://github.com/Arunasri-0096/beautyproducts.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t beautyproducts .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8090:8080 beautyproducts'
            }
        }

    }
}
