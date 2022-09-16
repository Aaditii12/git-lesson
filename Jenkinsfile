pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Aaditii12/git-lesson.git']]])
            }
        }
        stage('Build') { 
            steps {
                git 'https://github.com/Aaditii12/git-lesson.git'
                bat 'python Maths_Script.py'
            }
        }
        stage('Test') {
            steps {
                echo 'the job has been tested'
            }
        }
    }
}
