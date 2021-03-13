pipeline {

    agent any
    parameters {
        choice choices: ['prj1', 'prj2'], name: 'project'
    }

    stages {

        stage("checkout") {
            steps {
                dir('prj2') {
                    checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[credentialsId: 'f0fb50a2-9ba2-4dda-8724-86c508186338', url: 'https://github.com/zest9787/prj2.git']]])
                }
                dir('prj3') {
                    checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[credentialsId: 'f0fb50a2-9ba2-4dda-8724-86c508186338', url: 'https://github.com/zest9787/prj3.git']]])
                }
            }
        }
        stage("build") {
            steps {
                echo "building applications..... ${params.project}"
                withAnt(installation: 'ANT-1.10.9') {
                    dir("deploy") {
                        bat "ant ${params.project} -Dproject=${params.project}"
                    }
                }
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