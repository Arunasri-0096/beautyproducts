pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Arunasri-0096/beautyproducts.git'
            }
        }

        stage('Build Maven') {
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
                sh 'docker run -d -p 8089:8080 beautyproducts'
            }
        }

    }
}
