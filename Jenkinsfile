pipeline {

    agent any

    stages {

        stage("checkout") {
            steps {
                dir('prj2') {
                    checkout([$class: 'GitSCM', branches: [[name: 'master']], extensions: [], userRemoteConfigs: [[credentialsId: 'f0fb50a2-9ba2-4dda-8724-86c508186338', url: 'https://github.com/zest9787/prj2.git']]])
                }
                dir('prj3') {
                    checkout([$class: 'GitSCM', branches: [[name: 'master']], extensions: [], userRemoteConfigs: [[credentialsId: 'f0fb50a2-9ba2-4dda-8724-86c508186338', url: 'https://github.com/zest9787/prj3.git']]])
                }
            }
        }
        stage("build") {
            steps {
                echo "building applications....."
            }
        }
        stage("test") {
            steps {
                echo "test applications....."
            }
        }
        stage("deploy") {
            steps {
                echo "deploy applications....."
            }
        }
    }

}