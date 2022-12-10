pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Git clone') {
            steps {
               git branch: 'dev', url: 'https://github.com/DirektorBani/vector-role.git' 
            }
        }
        stage ('download molecule') {
            steps {
                sh 'pip3 install molecule molecule_docker'
            }
        }
        stage('run molecule') {
            steps {
                sh 'molecule test'
            }
        }
    }
}
