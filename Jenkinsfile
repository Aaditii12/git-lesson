pipeline {
    agent any
    parameters {
      booleanParam description: 'Select check box for python script will be run', name: 'TESTCASE_SELECTION'
    }
    options {
        skipDefaultCheckout(true)
    }

    stages {
        stage('CleanUp') {
            steps {
                cleanWs()
            }
        }
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
                echo "TESTCASE_SELECTION : ${params.TESTCASE_SELECTION}"
            }
        }
    }
}
