pipeline {
    agent any

    stages {

        stage('Git Clone') {
            steps {
                git branch 'main',https://github.com/Arunasri-0096/beautyproducts.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t yourdockerhub/beautyproducts .'
            }
        }

        stage('Docker Push') {
            steps {
                sh 'docker push yourdockerhub/beautyproducts'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8085:8080 yourdockerhub/beautyproducts'
            }
        }

    }
}
