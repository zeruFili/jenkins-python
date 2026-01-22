pipeline {
    agent {
        node {
            label 'docker-agent-python'
        }
    }

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                cd myapp
                pip3 install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Brad
                '''
            }
        }
    }
}
