pipeline {

    agent any

    tools {
        ANT 'ANT-1.10.9'
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
                echo "building applications....."
                withAnt(installation: 'ANT-1.10.9') {
                    dir("scoring") {
                        if (isUnix()) {
                            sh "ant deply/build.xml"
                        } else {
                            bat "ant deply/build.xml"
                        }
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