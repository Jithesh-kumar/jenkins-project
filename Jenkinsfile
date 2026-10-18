
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Jithesh-kumar/jenkins-project.git',
                    branch: 'main'
                sh 'ls -ltr'
            }
        }
      stage('Setup') {
    steps {
        sh '''
            rm -rf .venv

            python3.12 --version
            python3.12 -m venv .venv

            .venv/bin/python --version
            .venv/bin/python -m pip install --upgrade pip
            .venv/bin/python -m pip install -r requirements.txt
        '''
    }
}

stage('Test') {
    steps {
        sh '''
            .venv/bin/python --version
            .venv/bin/python -m pytest
            whoami
        '''
    }
}
    }
}
