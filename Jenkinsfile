pipeline {
    agent any

    stages {

        stage('Git Clone') {
            steps {
                git 'https://github.com/yourusername/beauty-products-devops.git'
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
