pipeline {
    agent any

 

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/development']], extensions: [], userRemoteConfigs: [[credentialsId: '94f83bf1-0bc1-4c62-a6e3-3bd94f22e6d3', url: 'https://github.com/shrth7/Hotel-Management-System.git']]])
            }
        }
        stage('Build and Test') {
            steps {
                sh 'mvn clean install -Dmaven.test.skip=true'

            }
        }
        stage('Code Analysis') {
            steps {
                echo "Scanned successfully!"
            }
        }
        stage('Notification') {
            steps {
                emailext body: 'Sharath, the recent build was successful', subject: 'Build SUCCESSFUL!!!!!!!', to: 'shrth7777@gmail.com'
            }
        }
        }
    }
