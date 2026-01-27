pipeline {
    agent any

    stages {
        stage('Code') {
            steps {
              git 'https://github.com/Biswa388/web-app.git'
            }
        }
        stage('code-build') {
            steps {
                 sh "mvn clean package"
            }
        }
        stage('Image-build') {
            steps {
                sh 'docker build -t tomcat:app .'
            }
        }
        stage('Deploy') {
            steps {
              sh 'docker run -itd --name app2 -p 8083:8080 tomcat:app'
            }
        }
    }
}
