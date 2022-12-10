pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Git clone') {
            steps {
                dir('freestyle') {
                git branch: 'dev', url: 'https://github.com/DirektorBani/vector-role.git' 
                }
            }
        }
        stage ('download molecule') {
            steps {
                sh 'pip3 install molecule molecule_docker'
            }
        }
        stage('run molecule') {
            steps {
                dir('freestyle') {
                sh 'molecule test -s centos8'
                }
            }
        }
    }
}
